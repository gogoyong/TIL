# Part 8. Handler
## Ch 2. Webpack
### 02. entry, output
### 03. plugins
webpack.config.js
```js
// import
const path = require('path')
const HtmlPlugIn = require('html-webpack-plugin')

// export
module.exports = {
  // parcel main.js
  // 파일을 읽어들이기 시작하는 진입점 설정
  entry: './js/main.js',

  // 결과물(번들)을 반환하는 설정
  output: {
    // path: path.resolve(__dirname, 'dist'),
    //dirname : 해당하는 파일의 실제경로를 나타내는 nodejs의 전역적 변수
    // filename: 'main.js',
    clean: true
  },

  // 번들링 후 결과물의 처리방식 중 다양한 플러그인들을 설정
  plugins: [
    new HtmlPlugIn({
      template: './index.html'
    })
  ],

  devServer: {
    host: 'localhost'
  }
}
// 배열데이터 [] array
// 객체데이터 {} object
```

  ### 05. module
  webpack.config.js

```js
module.exports {
  module: {
    rules: [{
      test: /\.css$/,
      // .css 로 끝나는 파일을 찾음
      use: [
        'style-loader',
        'css-loader'
        // 순서 : style로더부터써줌. 실제 로딩은 아래에서부터 로딩됨
      ]
    }]
  },
}
```

### 06. SCSS
### 07. Autoprefixer(PostCss)
### 08. Babel
```js
module.exports {
    module: {
      rules: [{
            test: /\.s?css$/,
            // (s를 포함할수도, 없을수도 있는) .css 로 끝나는 파일을 찾음
            use: [
              'style-loader', // HTML Style태그
              'css-loader',
              'postcss-loader',
              'sass-loader'
              // 순서 : style로더부터써줌. 실제 로딩은 아래에서부터 로딩됨
            ]
          },
          {
            test: /\.js$/,
            use: 'babel-loader'
          }
      }
}
```
### 09. Netlify 배포
### 10. NPX, Degit
git 저장소에 있던 프로젝트를 클론해오는 방법
npx degit gogoyong/webpack-template-basic webpack-template-test
npx degit 깃헙id/레포지토리명 폴더명


