---
description: '詳細情報: Platform:: IBoxArray インターフェイス'
title: Platform::IBoxArray インターフェイス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IBoxArray
- VCCORLIB/Platform::IBoxArray::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: 8b87a00d709bec8af016de4532c7c4ec759d72fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195145"
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray インターフェイス

`IBoxArray` はアプリケーション バイナリ インターフェイス (ABI) を越えて渡されるか、XAML コントロールなどの `Platform::Object^` 要素のコレクションに格納される値型の配列のラッパーです。

## <a name="syntax"></a>構文

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
各配列要素のボックス化された値の型。

### <a name="remarks"></a>解説

`IBoxArray` は、の C++/CX 名です `Windows::Foundation::IReferenceArray` 。

### <a name="members"></a>メンバー

`IBoxArray` インターフェイスは `IValueType` インターフェイスを継承します。 `IBoxArray` にも、次に示すメンバーがあります。

|Method|説明|
|------------|-----------------|
|[Value](#value)|以前にこの `IBoxArray` インスタンスに格納されていたことがあり、ボックス化が解除されている配列を返します。|

## <a name="iboxarrayvalue-property"></a><a name="value"></a> IBoxArray:: Value プロパティ

このオブジェクトに元から格納されていた値を返します。

### <a name="syntax"></a>構文

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ボックス化された値の型。

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

このオブジェクトに元から格納されていた値を返します。

### <a name="remarks"></a>解説

例については、「 [ボックス](../cppcx/boxing-c-cx.md)化」を参照してください。

## <a name="see-also"></a>関連項目

[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
