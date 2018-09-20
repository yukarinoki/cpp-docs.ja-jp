---
title: HandleT クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6622e92112d9f73e673e2fb44598a393843bf0fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396340"
---
# <a name="handlet-class"></a>HandleT クラス

オブジェクトへのハンドルを表します。

## <a name="syntax"></a>構文

```cpp
template <
   typename HandleTraits
>
class HandleT;
```

### <a name="parameters"></a>パラメーター

*HandleTraits*<br/>
インスタンス、 [HandleTraits](../windows/handletraits-structure.md)ハンドルの一般的な特性を定義する構造体。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`Traits`|`HandleTraits` と同義。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[HandleT::HandleT コンストラクター](../windows/handlet-handlet-constructor.md)|新しいインスタンスを初期化、 **HandleT**クラス。|
|[HandleT::~HandleT デストラクター](../windows/handlet-tilde-handlet-destructor.md)|インスタンスを初期化解除、 **HandleT**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[HandleT::Attach メソッド](../windows/handlet-attach-method.md)|現在の指定したハンドルに関連付けます**HandleT**オブジェクト。|
|[HandleT::Close メソッド](../windows/handlet-close-method.md)|現在の終了**HandleT**オブジェクト。|
|[HandleT::Detach メソッド](../windows/handlet-detach-method.md)|現在の関連付けを解除**HandleT**その基になるハンドルからオブジェクト。|
|[HandleT::Get メソッド](../windows/handlet-get-method.md)|基になるハンドルの値を取得します。|
|[HandleT::IsValid メソッド](../windows/handlet-isvalid-method.md)|示すかどうか、現在**HandleT**オブジェクト ハンドルを表します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[HandleT::InternalClose メソッド](../windows/handlet-internalclose-method.md)|現在の終了**HandleT**オブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[HandleT::operator= 演算子](../windows/handlet-operator-assign-operator.md)|指定した値に移動**HandleT**現在オブジェクト**HandleT**オブジェクト。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[HandleT::handle_ データ メンバー](../windows/handlet-handle-data-member.md)|表されるハンドルを含む、 **HandleT**オブジェクト。|

## <a name="inheritance-hierarchy"></a>継承階層

`HandleT`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)