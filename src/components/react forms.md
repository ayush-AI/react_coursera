# REACT

- ## Controlled forms using react

 - forms are standard way of taking data from the user.
 - forms element such as <input>, <textarea>, <button>, <select>
   maintain there own state in react and update it based on the 
   user input.
 
 - Controlled components are those components in which handlers functions are used to update the element state so that both the state are same.

 - In controlled form the state of both the form and component are so that every change will be reflected to the user.

### Example for Creating controlled forms.

- We are implementing the controlled forms in the contact component so that we will import some components from the reactstrap that will enable us   to

```
import { Breadcrumb, BreadcrumbItem,
            Button, Form, FormGroup, Label, Input, Col } from 'reactstrap'; 

```

note:- the component should be the class component because we need to update the state based on the input.

- the form which we are going to create is for taking feedback.So  
  the codes are according to that, hence learn it properly so that   you can create it for your used case.

- after creating the class component we will define some state in 
  the constructor using the below code.

```html

 constructor(props) {
        super(props);

        this.state = {
            firstname: '',
            lastname: '',
            telnum: '',
            email: '',
            agree: false,
            contactType: 'Tel.',
            message: ''
        };

        this.handleInputChange = this.handleInputChange.bind        (this);
        this.handleSubmit = this.handleSubmit.bind(this);
        
    }

    handleInputChange(event) {
        const target = event.target;
        const value = target.type === 'checkbox' ? target.checked         : target.value;
        const name = target.name;
    
        this.setState({
          [name]: value
        });
    }

    handleSubmit(event) {
        console.log('Current State is: ' + JSON.stringify        (this.state));
        alert('Current State is: ' + JSON.stringify(this.state));
        event.preventDefault();
    }

```

### Code snippets explained 
 - this.state represents the current state of the function.
 
 - handleInputChange is a method that is used for updating the 
  state of the form component so the change can be seen by the 
  user.
 - handleSubmit is the method for handeling the submission of the   form and preventing the page from reloading.

#### Meaning of the some code snippets

- <FormGroup row> here defines the one row of the form. 
- <Col md={10}> col in ReactStrap is same as the div tag in 
  bootStrap and the md={10} is as class col-md-10.
- htmlFor is used cause 'for' is reserved keyword in javascript.
- <FormGroup check> is used for checkboxes in the form.
- <Col md={{size:6, offset: 2}}> here we are two properties to the 
  element so we have to pass it as javascript object.

```html
 <div className="row row-content">
                   <div className="col-12">
                      <h3>Send us your Feedback</h3>
                   </div>
                    <div className="col-12 col-md-9">
                        <Form onSubmit={this.handleSubmit}>
                            <FormGroup row>
                                <Label htmlFor="firstname" md={2}                                    >First Name</Label>
                                <Col md={10}>
                                    <Input type="text"                                      id="firstname"                                       name="firstname"
                                        placeholder="First Name"
                                        value=                                                              {this.state.firstname}
                                        onChange=                                       {this.handleInputChange} />
                                </Col>
                            </FormGroup>
                            <FormGroup row>
                                <Label htmlFor="lastname" md={2}                                     >Last Name</Label>
                                <Col md={10}>
                                    <Input type="text"                                     id="lastname" name="lastname"
                                        placeholder="Last Name"
                                        value=                                         {this.state.lastname}
                                        onChange=                                       {this.handleInputChange} />
                                </Col>                        
                            </FormGroup>
                            <FormGroup row>
                            <Label htmlFor="telnum" md={2}>Contact                                Tel.</Label>
                                <Col md={10}>
                                    <Input type="tel" id="telnum"                                         name="telnum"
                                        placeholder="Tel. number"
                                        value={this.state.telnum}
                                        onChange=                                       {this.handleInputChange} />
                                </Col>
                            </FormGroup>
                            <FormGroup row>
                                <Label htmlFor="email" md={2}                                >Email</Label>
                                <Col md={10}>
                                    <Input type="email" id="email"                                         name="email"
                                        placeholder="Email"
                                        value={this.state.email}
                                        onChange=                                       {this.handleInputChange} />
                                </Col>
                            </FormGroup>
                            <FormGroup row>
                                <Col md={{size: 6, offset: 2}}>
                                    <FormGroup check>
                                        <Label check>
                                    <Input type="checkbox"
                                       name="agree"
                                       checked={this.state.agree}
                                          onChange= {this.handleInputChange} /> {' '}
                                            <strong>May we contact you?</strong>
                                        </Label>
                                    </FormGroup>
                                </Col>
                                <Col md={{size: 3, offset: 1}}>
                                    <Input type="select" name="contactType"
                                            value={this.state.contactType}
                                            onChange={this.handleInputChange}>
                                        <option>Tel.</option>
                                        <option>Email</option>
                                    </Input>
                                </Col>
                            </FormGroup>
                            <FormGroup row>
                                <Label htmlFor="message" md={2}>Your Feedback</Label>
                                <Col md={10}>
                                    <Input type="textarea"id="message" name="message"
                                        rows="12"
                                        value={this.state.message}
                                        onChange={this.handleInputChange}></Input>
                                </Col>
                            </FormGroup>
                            <FormGroup row>
                                <Col md={{size: 10, offset: 2}}>
                                    <Button type="submit" color="primary">
                                        Send Feedback
                                    </Button>
                                </Col>
                            </FormGroup>
                        </Form>
                    </div>
               </div>
```

### Simple form Validation 

- for the form validation we will import 'FormFeedback' from the 
  reactstrap.




