---
title: Platform::ValueType クラス
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: f4ce34fa3f197424833d34bdb866712d412e69c3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846551"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType クラス

値の型のインスタンスの基底クラス。

## <a name="syntax"></a>構文

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>パブリック メソッド

| 名前 | 説明 |
|--|--|
| [ValueType:: ToString](#tostring) | オブジェクトの文字列形式を返します。 [Platform:: Object](../cppcx/platform-object-class.md)から継承されます。 |

### <a name="remarks"></a>解説

ValueType クラスは、値型を構築するために使用されます。 ValueType は Object (基本メンバーを持つ) から派生します。 ただし、コンパイラは、それらのメンバーを、ValueType クラスから派生する値型からデタッチします。 値型がボックス化されると、コンパイラは、その基本メンバーを再びアタッチします。

### <a name="requirements"></a>必要条件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd

## <a name="valuetypetostring-method"></a><a name="tostring"></a> ValueType:: ToString メソッド

オブジェクトの文字列形式を返します。

### <a name="syntax"></a>構文

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>戻り値

値を表す Platform:: String。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
