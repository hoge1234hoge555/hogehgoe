function jsonChildToJSXChild(jsonChild) {
  if (jsonChild === null || typeof jsonChild === 'string') {
    return jsonChild;
  } else {
    const jsxChildren = jsonChildrenToJSXChildren(jsonChild.children);
    return {
      $$typeof: REACT_ELEMENT_TYPE,
      type: jsonChild.type,
      key: null,
      ref: null,
      props:
        jsxChildren === null
          ? jsonChild.props
          : {...jsonChild.props, children: jsxChildren},
      _owner: null,
      _store: __DEV__ ? {} : undefined,
    };
  }
}
