# React Native ESLint with Prettier

### Install packages
```
yarn add -D eslint-config-prettier eslint-plugin-prettier prettier
```

### .eslintrc.js
```
module.exports = {
  ...
  extends: ["@react-native-community", "plugin:prettier/recommended"]
};
```

That's it ;)
