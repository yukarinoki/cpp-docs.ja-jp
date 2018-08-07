---
title: FactoryCacheFlags 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
dev_langs:
- C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc4bd998368fb325878a81ee4954a2ceec9432fe
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570104"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 列挙型
ファクトリ オブジェクトをキャッシュするかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Remarks  
 既定では、出荷時のキャッシュ ポリシーとして指定、 [ModuleType](../windows/moduletype-enumeration.md)テンプレート パラメーターを作成するとき、[モジュール](../windows/module-class.md)オブジェクト。 このポリシーを上書きするには、指定、 **FactoryCacheFlags**ファクトリ オブジェクトを作成するときの値します。  
  
|||  
|-|-|  
|`FactoryCacheDefault`|キャッシュ ポリシー、`Module`オブジェクトを使用します。|  
|`FactoryCacheEnabled`|により、ファクトリをキャッシュに関係なく、`ModuleType`を作成するために使用するテンプレート パラメーターを`Module`オブジェクト。|  
|`FactoryCacheDisabled`|ファクトリをキャッシュに関係なく無効になります、`ModuleType`を作成するために使用するテンプレート パラメーターを`Module`オブジェクト。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)