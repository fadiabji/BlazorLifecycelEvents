# LifecycelEvents
lifecycle events in both server side and client side and the differences

//In Server Side the event cycle for parant and child component look like:  
// the sequance is like this:
        // parent - SetParameters
        // parent - OnInitialized
        // parent - OnParametersSet
                    // Child - SetParameters
                    // Child - OnInitialized
                    // Child _ OnParametersSet

    // parent - SetParameters
    // parent - OnInitialized
    // parent - OnParametersSet
                    // Child - SetParameters
                    // Child - OnInitialized
                    // Child _ OnParametersSet


    // Parent - OnAfterRender
                // Childe - OnAfterRender


 In Clinet Side  the Reslut look like:
   
    // The result from Devtool on browser
 //Parent- SetParametersAsycn : 2023-09-13:12:32:06.652
// Parent- OnInitialized : 2023-09-13:12:32:06.722
// Parent- OnParametersSet : 2023-09-13:12:32:06.723
        // Child- SetParametersAsycn : 2023-09-13:12:32:06.745
        // Child- OnInitialized : 2023-09-13:12:32:06.745
        // Child- OnParametersSet : 2023-09-13:12:32:06.745
// Parent- OnAfterRender : 2023-09-13:12:32:06.787
        // Child- OnAfterRender : 2023-09-13:12:32:06.787

// if you  have an event after first render it will render like this button in the parent component:
 // if you click the button It will not render all the page, just render this event you will see the reslut like this.

        // Parent- ClickMe button : 2023-09-13:12:45:51.116
        // Parent - ShouldRender : 2023 - 09 - 13:12:45:51.177
        // Parent - OnAfterRender : 2023 - 09 - 13:12:45:54.804
