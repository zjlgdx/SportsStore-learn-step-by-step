An exception of type 'System.ArrayTypeMismatchException' occurred in mscorlib.dll but was not handled in user code

Additional information: Attempted to access an element as a type incompatible with the array.

UPDATED WITH THE SOLUTION

Okay, this was very tricky. I have no idea how you manage to get this type of project. You might have upgraded your project type from an earlier version of ASP.NET MVC. Any way below is the answer.

In you Web.Config's runtime Assembly binding section, please add the below.

<dependentAssembly>
    <assemblyIdentity name="System.Web.Mvc" publicKeyToken="31bf3856ad364e35" />
    <bindingRedirect oldVersion="1.0.0.0-5.0.0.0" newVersion="5.0.0.0" />
</dependentAssembly>
This should fix your problem.

http://stackoverflow.com/questions/20436272/unity-bootstrapper-from-nuget-is-throwing-error-on-app-start

===