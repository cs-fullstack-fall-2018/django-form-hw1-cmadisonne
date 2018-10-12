# django-form-hw1

Watch the video here: https://youtu.be/6oOHlcHkX2U

Below, write out how to create a form in a new views method using any of the classes/models we used today.

# Model Form

class MovieForm(forms.ModelForm):

  class Meta:
  
    model = Movie
    
    fields = [
    
      'name',
      
      'yearReleased',
      
      'rated',
      
      'genre'
    ]

# View

def movie_view (request):

  form = MovieForm(request.POST or None)
  
  if form.isvalid ():
  
  form.save()
  
  form = MovieForm()
  
  context = {'form':form}
  
  return render(request, 'movieApp/form.html', context)
  
