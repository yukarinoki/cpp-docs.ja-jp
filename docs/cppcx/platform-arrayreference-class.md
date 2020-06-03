---
title: Platform::ArrayReference クラス
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: e9dd16ad6c3f53c5562b0419197a582c06fbc642
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354787"
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
|[配列参照::配列参照](#ctor)|`ArrayReference` クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[配列参照::演算子() 演算子](#operator-call)|この `ArrayReference` を `Platform::Array<T>^*`に変換します。|
|[ArrayReference::operator= 演算子](#operator-assign)|このインスタンスに別の `ArrayReference` の内容を割り当てます。|

## <a name="exceptions"></a>例外

### <a name="remarks"></a>解説

`ArrayReference` を使用して C スタイル配列にデータを格納する方法であれば、一度 `Platform::Array` 変数にコピーしたうえで改めて C スタイル配列にコピーするような余分な操作が不要になります。 `ArrayReference`を使用した場合には、コピー操作が 1 回のみとなります。 コード例については、「[配列と WriteOnlyArray」](../cppcx/array-and-writeonlyarray-c-cx.md)を参照してください。

### <a name="requirements"></a>必要条件

**サポートされる最小クライアント:** ウィンドウズ 8

**サポートされる最小サーバー:** ウィンドウズ サーバー 2012

**名前空間:** Platform

**ヘッダー:** vccorlib.h

## <a name="arrayreferencearrayreference-constructor"></a><a name="ctor"></a>配列参照::配列参照コンストラクター

[クラス](../cppcx/platform-arrayreference-class.md)の新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>パラメーター

*データ引数*<br/>
配列データへのポインター。

*サイズArg*<br/>
ソース配列の要素数。

*その他の引数*<br/>
新しいインスタンスを初期化するためにデータが移動される `ArrayReference` オブジェクト。

### <a name="remarks"></a>解説

## <a name="arrayreferenceoperator-operator"></a><a name="operator-assign"></a>配列参照::演算子= 演算子

移動セマンティクスを使用して、指定したオブジェクトを現在の[プラットフォーム::ArrayReference](../cppcx/platform-arrayreference-class.md)オブジェクトに割り当てます。

### <a name="syntax"></a>構文

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>パラメーター

*その他の引数*<br/>
現在の `ArrayReference` オブジェクトに移動されたオブジェクト。

### <a name="return-value"></a>戻り値

`ArrayReference` 型のオブジェクトへの参照。

### <a name="remarks"></a>解説

`Platform::ArrayReference` は、ref クラスではなく、標準 C++ クラス テンプレートです。

## <a name="arrayreferenceoperator-operator"></a><a name="operator-call"></a>配列参照::演算子() 演算子

現在の[プラットフォーム::配列参照](../cppcx/platform-arrayreference-class.md)オブジェクトを[プラットフォーム::配列](../cppcx/platform-array-class.md)クラスに変換します。

### <a name="syntax"></a>構文

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>戻り値

`Array<TArg>^` 型のオブジェクトへのハンドル。

### <a name="remarks"></a>解説

[プラットフォーム::配列参照](../cppcx/platform-arrayreference-class.md)は、標準の C++ クラス テンプレートであり、[プラットフォーム::配列](../cppcx/platform-array-class.md)は ref クラスです。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
