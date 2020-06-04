---
title: basic_iostream クラス
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: e2a892525afbbad6d5b42d0b836fee096a70c297
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376820"
---
# <a name="basic_iostream-class"></a>basic_iostream クラス

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

## <a name="remarks"></a>解説

クラス テンプレートは、基本クラス[basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`、>、`Tr`および抽出を通じて、その基本クラス[basic_istream](../standard-library/basic-istream-class.md)< `Elem`> を通じて`Tr`挿入を制御するオブジェクトを記述します。 2 つのオブジェクトは、共通の仮想[basic_ios](../standard-library/basic-ios-class.md)< `Elem`基本クラス`Tr`basic_ios を共有>。 また、これらは共通のストリーム バッファーを管理します。このストリーム バッファーには、`Elem` 型の要素が含まれ、その文字特性は `Tr` クラスによって決定されます。 コンストラクターは `basic_istream`( **strbuf**) および `basic_ostream`( **strbuf**) を使用して基底クラスを初期化します。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_iostream](#basic_iostream)|`basic_iostream` オブジェクトを作成します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[スワップ](#swap)|指定された `basic_iostream` オブジェクトの内容を、このオブジェクトの内容と交換します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_eq)|このオブジェクトに、指定された `basic_iostream` オブジェクトの値を代入します。 これは、`rvalue` が関係する移動代入で、コピーを残しません。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<istream>

**名前空間:** std

## <a name="basic_iostreambasic_iostream"></a><a name="basic_iostream"></a>basic_iostream::basic_iostream

`basic_iostream` オブジェクトを作成します。

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>パラメーター

*ストルブフ*\
既存の `basic_streambuf` オブジェクトです。

*そうです*\
新しい `basic_iostream` の構築に使用される既存の `basic_iostream` オブジェクト

### <a name="remarks"></a>解説

最初のコンストラクターが `basic_istream(strbuf)` および `basic_ostream(strbuf)` を使用してベース オブジェクトを初期化します。

2 番目のコンストラクターは、 を呼`move(right)`び出して基本オブジェクトを初期化します。

## <a name="basic_iostreamoperator"></a><a name="op_eq"></a>basic_iostream::演算子=

このオブジェクトに、指定された `basic_iostream` オブジェクトの値を割り当てます。 これは、右辺値が関係する移動代入で、コピーを残しません。

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
割り当て元の `basic_iostream` オブジェクトへの `rvalue` 参照。

### <a name="remarks"></a>解説

メンバ オペレータは`swap(right)`を呼び出します。

## <a name="basic_iostreamswap"></a><a name="swap"></a>basic_iostream::スワップ

指定された `basic_iostream` オブジェクトの内容を、このオブジェクトの内容と交換します。

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する `basic_iostream` オブジェクト。

### <a name="remarks"></a>解説

メンバー関数が呼`swap(right)`び出します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
