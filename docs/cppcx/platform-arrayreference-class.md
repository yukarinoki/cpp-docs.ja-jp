---
title: Platform::ArrayReference クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: 923f60e90517e377b99d5e29f38c48b2633c3c46
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742983"
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference クラス

`ArrayReference` は、C スタイル配列に入力データを格納するときに、入力パラメーターの [Platform::Array^](../cppcx/platform-array-class.md) と置き換えることができる最適化の種類です。

## <a name="syntax"></a>構文

```cpp
class ArrayReference
```

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ArrayReference::ArrayReference](#ctor)|`ArrayReference` クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ArrayReference::operator() 演算子](#operator-call)|この `ArrayReference` を `Platform::Array<T>^*`に変換します。|
|[ArrayReference::operator= 演算子](#operator-assign)|このインスタンスに別の `ArrayReference` の内容を割り当てます。|

## <a name="exceptions"></a>例外

### <a name="remarks"></a>Remarks

`ArrayReference` を使用して C スタイル配列にデータを格納する方法であれば、一度 `Platform::Array` 変数にコピーしたうえで改めて C スタイル配列にコピーするような余分な操作が不要になります。 `ArrayReference`を使用した場合には、コピー操作が 1 回のみとなります。 コード例では、次を参照してください。 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)します。

### <a name="requirements"></a>必要条件

**最小値には、クライアントがサポートされています。** Windows 8

**最小値には、サーバーがサポートされています。** Windows Server 2012

**名前空間:** プラットフォーム

**ヘッダー:** vccorlib.h

## <a name="ctor"></a>  Arrayreference::arrayreference コンス トラクター

新しいインスタンスを初期化、 [platform::arrayreference](../cppcx/platform-arrayreference-class.md)クラス。

### <a name="syntax"></a>構文

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>パラメーター

*dataArg*<br/>
配列データへのポインター。

*sizeArg*<br/>
ソース配列の要素数。

*otherArg*<br/>
新しいインスタンスを初期化するためにデータが移動される `ArrayReference` オブジェクト。

### <a name="remarks"></a>Remarks

## <a name="operator-assign"></a>  Arrayreference::operator = 演算子

現在、指定したオブジェクトを割り当てます[platform::arrayreference](../cppcx/platform-arrayreference-class.md)移動セマンティクスを使用してオブジェクト。

### <a name="syntax"></a>構文

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>パラメーター

*otherArg*<br/>
現在の `ArrayReference` オブジェクトに移動されたオブジェクト。

### <a name="return-value"></a>戻り値


  `ArrayReference` 型のオブジェクトへの参照。

### <a name="remarks"></a>Remarks

`Platform::ArrayReference` は、ref クラスではなく、標準 C++ クラス テンプレートです。

## <a name="operator-call"></a>  ArrayReference::operator() Operator

現在の変換[platform::arrayreference](../cppcx/platform-arrayreference-class.md)にオブジェクトを[platform::array](../cppcx/platform-array-class.md)クラス。

### <a name="syntax"></a>構文

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>戻り値

`Array<TArg>^` 型のオブジェクトへのハンドル。

### <a name="remarks"></a>Remarks

[Platform::arrayreference](../cppcx/platform-arrayreference-class.md)と[platform::array](../cppcx/platform-array-class.md)標準の C++ クラス テンプレートでない ref クラスが。

## <a name="see-also"></a>関連項目

[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)
