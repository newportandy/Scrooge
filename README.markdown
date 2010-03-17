Scrooge
=======
Scrooge is a module that blocks inheritance, it adds a simple hook that 
raises an exception whenever the class is subclassed. It's just about the simplest 
metaprogramming you'll ever see and there are a number of way to subvert it without 
even delving into monkeypatching. That said it illustrates a few key points, including
Ruby's fantastic use of hooks, in this case the ones that are called during class 
and object creation.

Try this:
    
    require 'scrooge'
    
    class Grandad
    end
    
    class Dad < Grandad
      include Scrooge
    end
    
    class Son < Dad
    end
