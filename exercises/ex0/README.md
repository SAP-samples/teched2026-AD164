# Level 1 Introduction to SAP Managed n8n and Intent based development.

In this exercise, you will learn how SAP provides n8n as a SAP managed solution through Joule studio,how it generates business solutions using Intent based development powered by SAP knowledge systems,Lean IX and Webagen.

## Level 2 SAP Managed n8n

SAP Business AI Platform provides agentic workflow capabilities and n8n is SAP agentic workflow orchestration solution part of Joule studio.It leverages n8n as a modern agentic workflow solution, scalable and robust SAP infrastructure  and AI driven development using LLMs and SAP knowledge systems.

1.	Click here.
<br>![](/exercises/ex0/images/00_00_0010.png)

2.	Insert this code.
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
