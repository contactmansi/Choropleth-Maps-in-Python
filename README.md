# Choropleth Maps in Python
 Plot Choropleth maps in Python using Plotly and Cufflinks

## Choropleth Maps - Summary
### Step 1: Import and Set-up - plotly and cufflinks

    from plotly.offline import download_plotlyjs, init_notebook_mode, plot, iplot
    import chart_studio.plotly as py
    init_notebook_mode(connected=True)
    import plotly.graph_objs as go
    import cufflinks as cf
    cf.go_offline()

USE THE PLOTLY CHEAT SHEET

### Step 2: 2 main dictionary objects - data and layout
#### Step 2.1: data dict() object
Begin with building a data dictionary. Easiest way to do this is to use the dict() function with the follwoing key/value pairs:

- type = 'choropleth',
- locations = list of abbreviation codes of states
- locationmode = 'USA-states'
- colorscale=
Either a predefined string such as given below or create a custom colorscale:
'pairs' | 'Greys' | 'Greens' | 'Bluered' | 'Hot' | 'Picnic' | 'Portland' | 'Jet' | 'RdBu' | 'Blackbody' | 'Earth' | 'Electric' | 'YIOrRd' | 'YIGnBu'


- text= list or array of text to display corresponding to locations
- z= array of values on z axis (color of state)
- colorbar = {'title':'Colorbar Title here'})

#### Step 2.2: Layout dict() object
Create the layout nested dictionary: geo dictionary is nested within layout which has 'scope' as a key and 'usa' as value for this example. 'geo' defines the geographic scope of the map's layout

    layout = dict(geo = {'scope':'usa'})
    
### Step 3: Using go.figure() Set up the choromap object that finally gets passed into iplot() for plotting

    choromap = go.Figure(data = [data],layout = layout)

### Step 4: plot the choromap
    iplot(choromap) # within the jupyter notebook
    plot(choromap) # to open choromap as an HTML file outside the NB in the browser

USA vs WORLD
change in key,value pairs of data and layout dictionaries below
