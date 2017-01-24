SuperLayout
===========

SuperLayout is a library that adds a few custom operators to Swift that makes using the new NSLayoutAnchor API in iOS 9 much less verbose and a pleasure to use. It doesn't override already-defined methods in `Equatable` (such as `==` and `>=`), like other frameworks do, and defines ones that are logical and easily understandable to anyone who might be inheriting your codebase or joining your team. The `equalTo` operator is just a `~`, and the greater than or equal to and less than or equal to operators are just `Option` + `<` and `Option` + `>`, respectively.

In short, turn this:

<img src='old1.png' width='589px' />

Into this:

<img src='new1.png' width='355px' />

Installation
------------

SuperLayout is available via CocoaPods and SwiftPM. In your Podfile, just specify:

    pod 'SuperLayout', '~> 0.2'

Before You Use
--------------

To use this library, you should have a basic understanding of the [`NSLayoutAnchor` API](https://developer.apple.com/reference/uikit/nslayoutanchor). If not, read up, and then check out the reference below to get started.

Reference
---------

#### [constraint(equalTo:)](https://developer.apple.com/reference/uikit/nslayoutanchor/1500946-constraint)

➥ `viewA.rightAnchor ~~ viewB.leftAnchor`

<details>
  <summary>See original</summary>

  ```swift
  viewA.rightAnchor.constraint(equalTo: viewB.leftAnchor).isActive = true
  ```

</details>

---

#### [constraint(equalTo:constant:)](https://developer.apple.com/reference/uikit/nslayoutanchor/1500937-constraint)

➥ `viewA.rightAnchor ~~ viewB.leftAnchor + C`

<details>
  <summary>See original</summary>

  ```swift
  viewA.rightAnchor.constraint(equalTo: viewB.leftAnchor, constant: C).isActive = true
  ```

</details>

---

#### [constraint(greaterThanOrEqualTo:)](https://developer.apple.com/reference/uikit/nslayoutanchor/1500936-constraint)

➥ `viewA.rightAnchor ≥≥ viewB.leftAnchor`

<details>
  <summary>See original</summary>

  ```swift
  viewA.rightAnchor.constraint(greaterThanOrEqualTo: viewB.leftAnchor).isActive = true
  ```

</details>

---

#### [constraint(greaterThanOrEqualTo:constant:)](https://developer.apple.com/reference/uikit/nslayoutanchor/1500948-constraint)

➥ `viewA.rightAnchor ≥≥ viewB.leftAnchor + C`

<details>
  <summary>See original</summary>

  ```swift
  viewA.rightAnchor.constraint(greaterThanOrEqualTo: viewB.leftAnchor, constant: C).isActive = true
  ```

</details>

---

#### [constraint(lessThanOrEqualTo:)](https://developer.apple.com/reference/uikit/nslayoutanchor/1500953-constraint)

➥ `viewA.rightAnchor ≤≤ viewB.leftAnchor`

<details>
  <summary>See original</summary>

  ```swift
  viewA.rightAnchor.constraint(lessThanOrEqualTo: viewB.leftAnchor).isActive = true
  ```

</details>

---

#### [constraint(lessThanOrEqualTo:constant:)](https://developer.apple.com/reference/uikit/nslayoutanchor/1500959-constraint)

➥ `viewA.rightAnchor ≤≤ viewB.leftAnchor + C`

<details>
  <summary>See original</summary>

  ```swift
  viewA.rightAnchor.constraint(lessThanOrEqualTo: viewB.leftAnchor, constant: C).isActive = true
  ```

</details>

---

Likewise, you can set heights, widths, and add constants and multipliers just as with the standard Auto Layout API.

```swift
viewA.widthAnchor ~~ 50
```

<details>
  <summary>See original</summary>

  ```swift
  viewA.widthAnchor.constraint(equalToConstant: 50).isActive = true
  ```

</details>

```swift
viewA.widthAnchor ≥≥ viewA.widthAnchor * 1.2 + 20
```

<details>
  <summary>See original</summary>

  ```swift
  viewA.widthAnchor.constraint(greaterThanOrEqualTo: viewA.widthAnchor, multiplier: 1.2, constant: 20).isActive = true
  ```

</details>

```swift
viewA.centerYAnchor ~~ view.centerYAnchor - 20
```

<details>
  <summary>See original</summary>

  ```swift
  viewA.centerYAnchor.constraint(lessThanOrEqualTo: view.centerYAnchor, multiplier: 1, constant: -20).isActive = true
  ```

</details>

