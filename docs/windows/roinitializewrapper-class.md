---
title: RoInitializeWrapper クラス |Microsoft Docs
ms.custom: ''
ms.date: 05/20/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f5c47ac34d8b159e75acf672ba57ca8c1ebac1e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592830"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper クラス

Windows ランタイムを初期化します。

## <a name="syntax"></a>構文

```cpp
class RoInitializeWrapper
```

## <a name="remarks"></a>Remarks

**RoInitializeWrapper**は利便性には、Windows ランタイムを初期化し、操作が成功したかどうかを示す HRESULT を返します。 クラスのデストラクターを呼び出すため、 `::Windows::Foundation::Uninitialize`、インスタンスの**RoInitializeWrapper**グローバルまたは最上位のスコープで宣言する必要があります。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[RoInitializeWrapper::RoInitializeWrapper コンストラクター](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|新しいインスタンスを初期化、 **RoInitializeWrapper**クラス。|
|[RoInitializeWrapper::~RoInitializeWrapper デストラクター](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|現在のインスタンスを破棄、 **RoInitializeWrapper**クラス。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[RoInitializeWrapper::HRESULT() 演算子](../windows/roinitializewrapper-hresult-parens-operator.md)|によって生成された HRESULT を取得、 **RoInitializeWrapper**コンス トラクター。|

## <a name="inheritance-hierarchy"></a>継承階層

`RoInitializeWrapper`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)