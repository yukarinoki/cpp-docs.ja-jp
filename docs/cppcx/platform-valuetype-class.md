---
title: Platform::ValueType クラス
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: 57fb089f0d9dc53ba8a65cef41e3341168ffea45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596405"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType クラス

値の型のインスタンスの基底クラス。

## <a name="syntax"></a>構文

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|[ValueType::ToString](#tostring)|オブジェクトの文字列形式を返します。 継承された[platform::object](../cppcx/platform-object-class.md)します。|

### <a name="remarks"></a>Remarks

ValueType クラスは、値型を構築するために使用されます。 ValueType は Object (基本メンバーを持つ) から派生します。 ただし、コンパイラは、それらのメンバーを、ValueType クラスから派生する値型からデタッチします。 値型がボックス化されると、コンパイラは、その基本メンバーを再びアタッチします。

### <a name="requirements"></a>必要条件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="tostring"></a> Valuetype::tostring メソッド

オブジェクトの文字列形式を返します。

### <a name="syntax"></a>構文

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>戻り値

値を表す platform::string を指定します。

## <a name="see-also"></a>関連項目

[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)