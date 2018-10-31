---
title: InterfaceList 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d9cbc1dfb31d744086e7a138521ae24f58e693f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788657"
---
# <a name="interfacelist-structure"></a>InterfaceList 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
インターフェイス名。再帰的なリストの先頭のインターフェイス。

*U*<br/>
インターフェイス名。再帰的なリストの残りのインターフェイスです。

## <a name="remarks"></a>Remarks

インターフェイスの再帰的な一覧を作成するために使用します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`FirstT`|テンプレート パラメーターのシノニム*T*します。|
|`RestT`|テンプレート パラメーターのシノニム*U*します。|

## <a name="inheritance-hierarchy"></a>継承階層

`InterfaceList`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)