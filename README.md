### SciRuby
---
#### daru pandas 
https://github.com/SciRuby/daru

#### statsample
https://github.com/sciruby/statsample

#### numo-narray numpy


```ruby
gem install daru

data_frame = Daru::DataFrame.new(
  {
    'Berr' => ['Kingfisher', 'Snow', 'Bud Light', 'Tiger Beer', 'Budweiser'],
    'Gallons sold' => [500, 400, 450, 200, 250]
  },
  index: ['India', 'China', 'USA', 'Malaysia', 'Canada']
)
data_frame

df = Daru::DataFrame.from_csv('TradeoffData.csv')
data_frame.row['USA']
data_frame['Beer']
data_frame.row['India'..'USA']
data_frame.first(2)
data_frame.last(2)
data_frame['Gallons produced'] = [550, 500, 600, 210, 240]
data_frame['Demand supply gap'] = data_frame['Gallons produced'] - data_frame['Gallons sold']
data_frame.where(data_frame['Gallons sold'].lt(300))
data_frame.where(
 data_frame['Beer']
 .in(['Snow', 'Kingfisher', 'Tiger Beer'])
 .and(
   data_frame['Gallons produced'].gt(520).or(data_frame['Gallons produced'].lt(250))
 )
)

data_frame.plot type: :bar, x: 'Beer', y: 'Gallons sold' do |plot, diagram|
  plot.x_label "Beer"
  plot.y_label "Gallons Sold"
  plot.yrange [0,600]
  plot.width 500
  plot.height 400
end

```

