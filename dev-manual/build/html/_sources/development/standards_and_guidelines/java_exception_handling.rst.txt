.. _java_exception_handling:

Java Exception Handling
=======================

Start by reading this article: http://www.codejava.net/java-core/exception/java-checked-and-unchecked-exceptions

Whenever possible, the application should utilize Checked exceptions.

The Following custom checked exceptions have been defined for the application and should be used
wherever appropriate:

* DataMappingException
* DataEntityNotFoundException
* DataPathNotFoundException
* PrincipalNotFoundException
* RequiredDataMissingException
* ConfigurationException
* DataEntityCreationException
* DataEntityUpdateException
* PropertyNotFoundException

All thrown exceptions should be explicitly caught, contextualized, logged and handled by the calling method.
The code snippet below shows how to properly catch, contextualize and log an exception.

.. code-block:: java

   try {
      // Some Code that throws a checked exception
   } catch (SomeException e) {
      String msg = "Exception occurred while trying to create a new FormType object in the JCR. Msg="+e.getMessage();
      LOGGER.error(msg);
      throw new DataEntityCreationException(msg, e);
   }

Notice the following about the approach followed:

* The Exception is given a simplistic name "e"
* A String parameter is built up containing relevant contextual information about the exception.
* The exception sctring is intended to be easily understood by someone who only has access to the log file and source code.
* The String message is logged using a Log4J ERROR level
* There is no e.printStackTrace()
* We don't dump stacktraces all over the show, generally just in the highest level of the stack (for example a SlingModel, or Servlet)
* In the Sling model the logging statement will be: LOGGER.error(msg, e);
* In this particular case, the method of handling the exception is to throw it up the call stack (with information about the cause)

"Handling" and exception can mean one of 3 things:

* (After adding context) throw the exception up the call stack
* Report the exception to the user. This will be done in the case of Servlets only
* Replace the data used and try again (or try another method)

Which exception Types to use where
----------------------------------

* ConstraintViolationException
    * Use this exception for constraint validation failures. For example: Can't create Form Type with code X, because another Form Type already exists with that code
    * Typically we log these at WARN level (and without a stacktrace) because these are not actual system errors








