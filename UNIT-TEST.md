# React Native Unit Testing with Jest

### Install packages
```
yarn add -D jest // if package doesn't installed by default
```

### Test-file.js template
```
import React from 'react';
import renderer from 'react-test-renderer';

// Components
import Component from '../Component';

describe('<Component />', () => {
	const defaultProps = {};
	const wrapper = renderer.create(<Component {...defaultProps} />);

	test('render', () => {
		expect(wrapper).toMatchSnapshot();
	});
});
```

or install **ES7 React/Redux/GraphQL/React-Native snippets** addons in vscode and use `stest` snippet

That's it ;)
