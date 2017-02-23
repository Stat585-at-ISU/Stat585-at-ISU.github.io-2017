---
title: "Creating an S3 class for pets"
author: "Kiegan Rice"
topic: "05"
layout: post
root: ../../../
---

Out of the two options for this blog post, I have decided to focus on the second one:  

## Explain how a user can define a new S3 class with objects and methods at a small example of your choice.  

I will define a new S3 class with objects and methods. This S3 class will be focused on Pets, so that I can keep track of the pets that live at my house.  


{% highlight r %}
Pets <- function(isMammal=TRUE,animalType="hedgehog",breedType="African Pygmy",exerciseToday=FALSE)
{
        me <- list(
                hasBabies = isMammal,
                petType = animalType,
                breed = breedType,
                hasExercisedToday = exerciseToday
       )
        class(me) <- append(class(me),"Pets")
        return(me)
}
{% endhighlight %}
Now that we have created this class, we can create new objects of this class by calling the function we have created. I will define two different pets (Obi and Oslo) using this class function.



{% highlight r %}
Obi <- Pets()
Obi
{% endhighlight %}



{% highlight text %}
## $hasBabies
## [1] TRUE
## 
## $petType
## [1] "hedgehog"
## 
## $breed
## [1] "African Pygmy"
## 
## $hasExercisedToday
## [1] FALSE
## 
## attr(,"class")
## [1] "list" "Pets"
{% endhighlight %}



{% highlight r %}
Oslo <- Pets(isMammal=TRUE, animalType="dog", breedType="Poochon", exerciseToday = FALSE)
Oslo
{% endhighlight %}



{% highlight text %}
## $hasBabies
## [1] TRUE
## 
## $petType
## [1] "dog"
## 
## $breed
## [1] "Poochon"
## 
## $hasExercisedToday
## [1] FALSE
## 
## attr(,"class")
## [1] "list" "Pets"
{% endhighlight %}
Now that we have created a class, we can create methods for this class. One example (similar to the example in the R tutorial) would be to set whether the pet has gotten exercise today.


{% highlight r %}
sethasExercisedToday <- function(Object, newValue)
        {
                print("Calling the base sethasExercisedToday function")
                UseMethod("sethasExercisedToday",Object)
                print("Note this is not executed!")
        }

sethasExercisedToday.default <- function(Object, newValue)
        {
                print("You screwed up. I do not know how to handle this object.")
                return(Object)
        }


sethasExercisedToday.Pets <- function(Object, newValue)
        {
                print("In sethasExercisedToday.Pets and setting the value")
                Object$hasExercisedToday <- newValue
                return(Object)
        }
{% endhighlight %}

This allows us to set whether a pet has gotten exercise today, so we can update that value once the pet gets exercise.  


{% highlight r %}
Oslo <- sethasExercisedToday(Oslo,TRUE)
{% endhighlight %}



{% highlight text %}
## [1] "Calling the base sethasExercisedToday function"
## [1] "In sethasExercisedToday.Pets and setting the value"
{% endhighlight %}



{% highlight r %}
Olso$hasExercisedToday
{% endhighlight %}



{% highlight text %}
## Error in eval(expr, envir, enclos): object 'Olso' not found
{% endhighlight %}
