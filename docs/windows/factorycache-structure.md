---
title: FactoryCache 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df2335a49d2d5daf862db7cea7eb413c01164bee
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609029"
---
# <a name="factorycache-structure"></a>FactoryCache 構造体

Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Remarks

クラス ファクトリと、登録されている wrt を識別する値または COM クラスのオブジェクトの場所が含まれています。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[FactoryCache::cookie データ メンバー](../windows/factorycache-cookie-data-member.md)|登録済み Windows ランタイムまたは COM クラスのオブジェクトを識別し、オブジェクトの登録を解除する際に使用する値が含まれています。|
|[FactoryCache::factory データ メンバー](../windows/factorycache-factory-data-member.md)|Windows ランタイムまたは COM クラス ファクトリを指します。|

## <a name="inheritance-hierarchy"></a>継承階層

`FactoryCache`

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)