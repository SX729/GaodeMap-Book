## REACT-AMAP创建方式
&emsp;&emsp;react-amap 是一个基于 React 封装的高德地图组件，提供的所有组件，都可以通过**events.created**方法获得原始的高德实例，然后按照高德的 API，对这些实例进行更复杂的操作。
```
import { Map, Marker } from 'react-amap';
class App extends React.Component {
  constructor() {
    super();
    this.amapEvents = {
      created: (mapInstance) => {
        console.log('高德地图 Map 实例创建成功；如果你要亲自对实例进行操作，可以从这里开始。比如：');
        console.log(mapInstance.getZoom());
      }
    };
    this.markerEvents = {
      created: (markerInstance) => {
        console.log('高德地图 Marker 实例创建成功；如果你要亲自对实例进行操作，可以从这里开始。比如：');
        console.log(markerInstance.getPosition());
      }
    }
    this.markerPosition = { longitude: 120, latitude: 30 };
  }
  render() {
    return <div style={{ width: '100%', height: '400px' }}>
      <Map events={this.amapEvents}>
        <Marker position={this.markerPosition} events={this.markerEvents} />
      </Map>
    </div>
  }
}
```
&emsp;&emsp;react-amap 的组件接收的属性中，有基本类型值和引用类型值，引用类型的属性，最好在 constructor 和 componentWillMount 阶段声明；然后在组件里引用这个变量：
```
class MapApp extends React.Component {
  constructor() {
    super();
    // Good Practice
    this.mapCenter = { longitude: 120, latitude: 30 };
  }

  render() {
    return <div style={{ width: 600, height: 400 }}>
      <Map zoom={5} center={this.mapCenter}/>
    </div>
  }
}
```
[REACT-AMAP地址](https://elemefe.github.io/react-amap/articles/practice)