# React-Native를 이용할 때 차트 생성하는 방법

## 사용한 패키지
react-native-chart-kit
[link: https://www.npmjs.com/package/react-native-chart-kit]

## 패키지 설치
yarn add react-native-chart-kit
yarn add react-native-svg

## 패키지 임포트
import {
  LineChart,
  BarChart,
  PieChart,
  ProgressChart,
  ContributionGraph,
  StackedBarChart
} from "react-native-chart-kit";

## 사용법
### LINECHART
Component
  <LineChart
    data={{
      labels: ["January", "February", "March", "April", "May", "June"],
      datasets: [
        {
          data: [
            Math.random() * 100,
            Math.random() * 100,
            Math.random() * 100,
            Math.random() * 100,
            Math.random() * 100,
            Math.random() * 100
          ]
        }
      ]
    }}
    width={Dimensions.get("window").width} // from react-native
    height={220}
    yAxisLabel="$"
    yAxisSuffix="k"
    yAxisInterval={1} // optional, defaults to 1
    chartConfig={{
      backgroundColor: "#e26a00",
      backgroundGradientFrom: "#fb8c00",
      backgroundGradientTo: "#ffa726",
      decimalPlaces: 2, // optional, defaults to 2dp
      color: (opacity = 1) => `rgba(255, 255, 255, ${opacity})`,
      labelColor: (opacity = 1) => `rgba(255, 255, 255, ${opacity})`,
      style: {
        borderRadius: 16
      },
      propsForDots: {
        r: "6",
        strokeWidth: "2",
        stroke: "#ffa726"
      }
    }}
    bezier
    style={{
      marginVertical: 8,
      borderRadius: 16
    }}
  />
 Style Object
  const chartConfig = {
  backgroundGradientFrom: "#1E2923",
  backgroundGradientFromOpacity: 0,
  backgroundGradientTo: "#08130D",
  backgroundGradientToOpacity: 0.5,
  color: (opacity = 1) => `rgba(26, 255, 146, ${opacity})`,
  strokeWidth: 2, // optional, default 3
  barPercentage: 0.5,
  useShadowColorFromDataset: false // optional
};
 
Properties
 |Property|Type|Description|
 |---|---|---|
|backgroundGradientFrom|string|Defines the first color in the linear gradient of a chart's background|
|backgroundGradientFromOpacity|Number	Defines the first color opacity in the linear gradient of a chart's background|
|backgroundGradientTo	string|Defines the second color in the linear gradient of a chart's background|
|backgroundGradientToOpacity|Number	Defines the second color opacity in the linear gradient of a chart's background|
|fillShadowGradient	string|Defines the color of the area under data|
|fillShadowGradientOpacity|Number	Defines the initial opacity of the area under data|
|useShadowColorFromDataset|Boolean	Defines the option to use color from dataset to each chart data. Default is false|
|color|function => string|Defines the base color function that is used to calculate colors of labels and sectors used in a chart|
|strokeWidth|Number|Defines the base stroke width in a chart|
|barPercentage|Number|Defines the percent (0-1) of the available width each bar width in a chart|
|barRadius|Number|Defines the radius of each bar|
|propsForBackgroundLines|props|Override styles of the background lines, refer to react-native-svg's Line documentation|
|propsForLabels|props|Override styles of the labels, refer to react-native-svg's Text documentation|
|propsForVerticalLabels|props|Override styles of vertical labels, refer to react-native-svg's Text documentation|
|propsForHorizontalLabels|props|Override styles of horizontal labels, refer to react-native-svg's Text documentation|
