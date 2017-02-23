---
title: "The S3 class system"
author: "Ashish Jain"
topic: "05"
layout: post
root: ../../../
---

#Explain how a user can define a new S3 class with objects and methods at a small example of your choice.

Before going through this material, I was not aware of the fact that R also uses object oriented programming (OOPs) concepts which are one of the main highlights of C++ and Java. I know these concepts are really important in designing and developing. In R, there are three object-oriented systems including S3, S4, and R5. In this post, I am going to show a basic workflow of defining and designing S3 system. In my example, I am going to define a DNASequence class which store a DNA Sequence and has methods which are used to analyze the DNA Sequence.

##Creating an S3 class
In this example, we are using the basic approach in which we are defining a `DNASequence` method which will first store some information about the `DNASequence` class in a list and then changes the class name of the list to DNASequence and return this `DNASequence` object.


{% highlight r %}
#Class for doing various functions on a DNA sequence
DNASequence <- function(sequence,type) {
   out <- list(seq=sequence,type=type)
   #class(out) <- append(class(out),"DNASequence")
   class(out) <-"DNASequence"
   invisible(out)
}
{% endhighlight %}


##Create methods to analyze the DNASequence object
In this step, we are creating methods associated with the `DNASequence` class. The approach which we are using is to define a function that exists outside of the class. In this, we are only defining the function for our specific `DNASequence` class. We can also define a method in a more generic way, and then a function specific to our class. In that case, the R environment chooses which function to invoke based on the type of the class of the argument. In our case, we defined three different functions which analyze the DNA sequence. The first function calculates the A (Adenine), T (Thymine), G (Guanine), C (Cytosine) base content in the DNA sequence. The second functions calculate the GC-rich content of the sequence which helps in studying bias in DNA repair and other processes. The final method searches a particular biologically important motif or conserved sequence in the given DNA Sequence.


{% highlight r %}
#Count ATGC content
getATGCContent<-function(sequence)
{
  UseMethod("getATGCContent",sequence)
}
getATGCContent.DNASequence <- function(sequence){
                sequence_split <- strsplit(sequence$seq, "")[[1]]
                Acount = Gcount = Ccount = Tcount = 0;
                for(i in sequence_split)
                {
                  if(i == 'A'){
                    Acount = Acount + 1
                  }else if(i == 'T'){
                    Tcount = Tcount + 1
                  } else if(i == 'G'){
                    Gcount = Gcount + 1
                  } else if(i == 'C')
                  {
                    Ccount = Ccount + 1
                  }
                }
                return(data.frame(A=Acount,T=Tcount,G=Gcount,C=Ccount))
        }

#Calculate GC content
getGCContent<-function(sequence)
{
  UseMethod("getGCContent",sequence)
}
getGCContent.DNASequence <- function(sequence)
{
                nGCs<-letterFrequency(BString(sequence$seq),"GC")
                percentage<-(nGCs/(length(strsplit("ATGCATGCATGCAATTGGCCATGCATGC", "")[[1]])))*100
                return(paste0("GC content in this sequence is ",percentage,"%"))
}

#motif searching
getMotifs<-function(sequence,motif)
{
  UseMethod("getMotifs",sequence)
}
getMotifs.DNASequence <- function(sequence,motif)
        {
                pos = gregexpr(motif, sequence$seq)
                if(pos[[1]][1] == -1)
                {
                  print("Motif Not found.")
                }else
                {
                print("Motif found at positions ")
                print(pos[[1]])
                }
}
{% endhighlight %}

##Creating DNASequence object and using class methods to analyze DNA Sequence

{% highlight r %}
seq.object <- DNASequence("ATGCATGCATGCAATTGGCCATGCATGC","exon")
getGCContent(seq.object)
{% endhighlight %}



{% highlight text %}
## [1] "GC content in this sequence is 50%"
{% endhighlight %}



{% highlight r %}
getATGCContent(seq.object)
{% endhighlight %}



{% highlight text %}
##   A T G C
## 1 7 7 7 7
{% endhighlight %}



{% highlight r %}
getMotifs(seq.object,"AT")
{% endhighlight %}



{% highlight text %}
## [1] "Motif found at positions "
## [1]  1  5  9 14 21 25
## attr(,"match.length")
## [1] 2 2 2 2 2 2
## attr(,"useBytes")
## [1] TRUE
{% endhighlight %}
