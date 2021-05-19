#Expo를 이용해서 애플리케이션 개발시 이슈 모음

### Tried to register two views with the same name RNCSafeAreaProvider
이슈 발생 : expo install expo-font 이후
원인 분석 : expo-font는 react-native-gesture-handler 패키지와 중복사항을 포함하고 있음
이슈 해결 : yarn add react-native-gesture-handler 재설치시 문제 해결됨

### Android permissions
이슈 발생 : 앱이 마켓에서 삭제됨
원인 분석 : android 권한을 설정하지 않을 시에 expo는 android의 모든 권한을 default를 포함시켜 앱을 build 함
이슈 해결 : app.json에서 android에 "permissions":[] 를 추가 >> 최소한의 기본적인 권한만 포함시킴
