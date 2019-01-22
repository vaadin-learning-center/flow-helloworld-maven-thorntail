<center>
<a href="https://vaadin.com">
 <img src="https://vaadin.com/images/hero-reindeer.svg" width="200" height="200" /></a>
</center>

# HelloWorld - Vaadin - Ramp up in a second.
A nano project to start a Vaadin project.
Here you will get a project template based on one maven module.

To start the webapp use the following maven command.

```mvn clean install thorntail:run ```

> All tutorials are available under [https://vaadin.com/tutorials](https://vaadin.com/tutorials)

## target of this project
The target of this project is a minimal rampup time for a first hello world.
Why we need one more HelloWorld? Well, the answer is quite easy. 
If you have to try something out, or you want to make a small POC to present something,
there is no time and budget to create a demo project.
You don´t want to copy paste all small things together.
Here you will get a HelloWorld-Project that will give you all in a second.

Clone the repo and start editing the class ```VaadinApp```.
Nothing more. 

## Used Servlet container?
Here we are using the  **Thorntail Swarm**  from RedHat as Servlet-Container.
[https://thorntail.io/](https://thorntail.io/)

## The UI itself
The UI itself is has only a few elements. 
There is only a button you can click.
For every click, the counter will be increased.
For more information about the routing (**@Route(""")**), have a look at the orig documentation
[https://vaadin.com/docs/v10/flow/routing/tutorial-routing-annotation.html](https://vaadin.com/docs/v10/flow/routing/tutorial-routing-annotation.html)


```java
@Route("")
public class VaadinApp extends Composite<Div> implements HasLogger {

  private final Button         btnClickMe   = new Button("click me");
  private final Span           lbClickCount = new Span("0");
  private final VerticalLayout layout       = new VerticalLayout(btnClickMe, lbClickCount);

  private int clickcount = 0;

  public VaadinApp() {
    btnClickMe.addClickListener(event -> lbClickCount.setText(valueOf(++clickcount)));

    //set the main Component
    logger().info("setting now the main ui content..");
    getContent().add(layout);

  }
}
```

Happy Coding.

if you have any questions: ping me on Twitter [https://twitter.com/SvenRuppert](https://twitter.com/SvenRuppert)
or via mail.
