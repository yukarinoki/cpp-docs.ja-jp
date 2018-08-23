---
title: ChainInterfaces 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f0fc65d2aeab01de022e23d0645682800a7d555d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602366"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces 構造体

一連のインターフェイス ID に適用できる検証および初期化関数を指定します。

## <a name="syntax"></a>構文

```cpp
template <
   typename I0,
   typename I1,
   typename I2 = Details::Nil,
   typename I3 = Details::Nil,
   typename I4 = Details::Nil,
   typename I5 = Details::Nil,
   typename I6 = Details::Nil,
   typename I7 = Details::Nil,
   typename I8 = Details::Nil,
   typename I9 = Details::Nil
>
struct ChainInterfaces : I0;
template <
   typename DerivedType,
   typename BaseType,
   bool hasImplements,
   typename I1,
   typename I2,
   typename I3,
   typename I4,
   typename I5,
   typename I6,
   typename I7,
   typename I8,
   typename I9
>
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;
```

### <a name="parameters"></a>パラメーター

*I0*  
(必須)インターフェイス ID は 0 です。

*I1*  
(必須)ID 1 のインターフェイスです。

*I2*  
(省略可能)インターフェイス ID 2 です。

*I3*  
(省略可能)インターフェイス ID 3 です。

*I4*  
(省略可能)ID 4 のインターフェイスです。

*I5*  
(省略可能)ID 5 のインターフェイスです。

*I6*  
(省略可能)ID 6 のインターフェイスです。

*I7*  
(省略可能)インターフェイス ID 7 です。

*I8*  
(省略可能)インターフェイス ID 8 です。

*I9*  
(省略可能)インターフェイス ID は 9 です。

*DerivedType*  
派生型。

*BaseType*  
派生型の基本型。

*hasImplements*  
ブール値の場合に**true**、ため使用できません、 [MixIn](../windows/mixin-structure.md)構造から派生していないクラスを使用して、[実装](../windows/implements-structure.md)構造体。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ChainInterfaces::CanCastTo メソッド](../windows/chaininterfaces-cancastto-method.md)|指定されたインターフェイス ID をによって定義された特殊な形式をそれぞれにキャストできるかどうかを示す、 **ChainInterface**テンプレート パラメーター。|
|[ChainInterfaces::CastToUnknown メソッド](../windows/chaininterfaces-casttounknown-method.md)|によって定義された型のインターフェイス ポインターをキャスト、 *I0*へのポインターをテンプレート パラメーター`IUnknown`します。|
|[ChainInterfaces::FillArrayWithIid メソッド](../windows/chaininterfaces-fillarraywithiid-method.md)|ストアで定義されたインターフェイス ID、 *I0*インターフェイス Id の指定した配列内の指定した場所にテンプレート パラメーター。|
|[ChainInterfaces::Verify メソッド](../windows/chaininterfaces-verify-method.md)|各インターフェイスは、テンプレート パラメーターで定義されていることを確認します*I0*を通じて*I9*から継承`IUnknown`や`IInspectable`、および*I0*から継承。*I1*を通じて*I9*します。|

### <a name="protected-constants"></a>保護されている定数

|name|説明|
|----------|-----------------|
|[ChainInterfaces::IidCount 定数](../windows/chaininterfaces-iidcount-constant.md)|インターフェイスのテンプレート パラメーターで指定されたインターフェイスに含まれている Id の合計数*I0*を通じて*I9*します。|

## <a name="inheritance-hierarchy"></a>継承階層

`I0`

`ChainInterfaces`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)