---
title: Creatormap::factorycreator データ メンバー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
dev_langs:
- C++
helpviewer_keywords:
- factoryCreator data member
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90367a21d76fe7fe735d1174bc9b9d40900dec78
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600831"
---
# <a name="creatormapfactorycreator-data-member"></a>CreatorMap::factoryCreator データ メンバー

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
 IUnknown** factory);
```

### <a name="parameters"></a>パラメーター

*currentflags*  
1 つ、 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙子。

*entry*  
CreatorMap は。

*iidClassFactory*  
クラス ファクトリのインターフェイス ID。

*ファクトリ*  
操作が完了時は、クラス ファクトリのアドレス。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>Remarks

指定した CreatorMap のファクトリを作成します。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[CreatorMap 構造体](../windows/creatormap-structure.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)