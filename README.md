# React From Builder

## Installation
<pre>
  npm i zubair-react-form-builder
</pre>

![](zrfb-screenshot-1.png)

![](zrfb-screenshot-2.png)


## FormContainer Props
1. custom : Array
2. onSave(form) : Function

## ToolBox Props
1. custom : Array

## Example
You can pass custom components to the form builder
<pre>
const myCustoms = [
    {
        container : &lt ContainerComponent/&gt,
        preview : &lt PreviewComponent/&gt,
        toolbox : {
            title : 'Component',
            icon : 'fa fa-user',
            name : 'CUSTOM_COM'
        },
        states : {
            toolType: 'CUSTOM_COM',
            num1 : 1,
            num2 : 2
        }
    }
]

Simply pass myCustoms to
&lt FormContainer onSave={YOUR_METHOD} custom={ myCustoms } /&gt
&lt ToolBox custom={ myCustoms } /&gt
</pre>

## Required Props Methods Of Custom Component

1. this.props.changeValue(state, this.props.index)

2. this.props.removeField(index)

## Example Props Methods

<pre>
        // on change state
        changeValue(stateFor, value){
            switch (stateFor){
                case "TITLE" :
                    this.setState( { title : value } )
                    break;
                default:
                    return;
            };
            setTimeout(() => {
                return this.props.changeState(this.state, this.props.index);
            }, 0)
        }


        <input
            value={this.state.value}
            onChange={(e) => this.changeValue('TITLE', e.target.value)} />

         // on remove field   
        <span
            className='pull-right cross'
            onClick={() => this.props.removeField(this.props.index)}>x</span>

</pre>
