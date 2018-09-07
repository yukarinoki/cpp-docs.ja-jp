---
title: basic_iostream クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef4b993ec628771666ac3773b575ee518c18173
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106439"
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

## <a name="requirements"></a>要件

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

*strbuf*<br/>
既存の `basic_streambuf` オブジェクト。

*right*<br/>
新しい `basic_iostream` の構築に使用される既存の `basic_iostream` オブジェクト

### <a name="remarks"></a>Remarks

最初のコンストラクターが `basic_istream(strbuf)` および `basic_ostream(strbuf)` を使用してベース オブジェクトを初期化します。

2 番目のコンス トラクターを呼び出してベース オブジェクトを初期化します`move(right)`します。

## <a name="op_eq"></a>  basic_iostream::operator=

このオブジェクトに、指定された `basic_iostream` オブジェクトの値を割り当てます。 これは、右辺値が関係する移動代入で、コピーを残しません。

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
割り当て元の `basic_iostream` オブジェクトへの `rvalue` 参照。

### <a name="remarks"></a>Remarks

メンバーの演算子呼び出し`swap(right)`します。

## <a name="swap"></a>  basic_iostream::swap

指定された `basic_iostream` オブジェクトの内容を、このオブジェクトの内容と交換します。

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
交換する `basic_iostream` オブジェクト。

### <a name="remarks"></a>Remarks

メンバー関数の呼び出し`swap(right)`します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
