---
title: basic_iostream クラス
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: 052271e2e2cc929875489e27abde2147bc5c070a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460095"
---
# <a name="basiciostream-class"></a>basic_iostream クラス

入力と出力の両方を行うことができるストリーム クラス。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_iostream : public basic_istream<Elem, Tr>,
    public basic_ostream<Elem, Tr>
{
public:
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};
```

## <a name="remarks"></a>Remarks

このテンプレート クラスは、基底クラス [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`> を使用した挿入の制御、および基底クラス [basic_istream](../standard-library/basic-istream-class.md)< `Elem`, `Tr`> を使用した抽出の制御を行うオブジェクトを記述します。 2 つのオブジェクトは、仮想基底クラス [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`> を共有しています。 また、これらは共通のストリーム バッファーを管理します。このストリーム バッファーには、`Elem` 型の要素が含まれ、その文字特性は `Tr` クラスによって決定されます。 コンストラクターは `basic_istream`( **strbuf**) および `basic_ostream`( **strbuf**) を使用して基底クラスを初期化します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_iostream](#basic_iostream)|`basic_iostream` オブジェクトを作成します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[swap](#swap)|指定された `basic_iostream` オブジェクトの内容を、このオブジェクトの内容と交換します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator=](#op_eq)|このオブジェクトに、指定された `basic_iostream` オブジェクトの値を代入します。 これは、`rvalue` が関係する移動代入で、コピーを残しません。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<istream>

**名前空間:** std

## <a name="basic_iostream"></a>  basic_iostream::basic_iostream

`basic_iostream` オブジェクトを作成します。

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>パラメーター

*strbuf*\
既存の `basic_streambuf` オブジェクト。

*そうです*\
新しい `basic_iostream` の構築に使用される既存の `basic_iostream` オブジェクト

### <a name="remarks"></a>Remarks

最初のコンストラクターが `basic_istream(strbuf)` および `basic_ostream(strbuf)` を使用してベース オブジェクトを初期化します。

2番目のコンストラクターは、を呼び`move(right)`出すことによって、ベースオブジェクトを初期化します。

## <a name="op_eq"></a>  basic_iostream::operator=

このオブジェクトに、指定された `basic_iostream` オブジェクトの値を割り当てます。 これは、右辺値が関係する移動代入で、コピーを残しません。

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
割り当て元の `basic_iostream` オブジェクトへの `rvalue` 参照。

### <a name="remarks"></a>Remarks

このメンバー演算子は`swap(right)`、を呼び出します。

## <a name="swap"></a>  basic_iostream::swap

指定された `basic_iostream` オブジェクトの内容を、このオブジェクトの内容と交換します。

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する `basic_iostream` オブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数は`swap(right)`を呼び出します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
