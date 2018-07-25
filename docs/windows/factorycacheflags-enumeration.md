---
title: FactoryCacheFlags 列挙型 |Microsoft ドキュメント
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
ms.openlocfilehash: 5ba3d9b75ff72399e1b9a027c937c24bba4a6c37
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874331"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 列挙型
ファクトリ オブジェクトをキャッシュするかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>コメント  
 既定では、ポリシーをキャッシュ ファクトリとして指定されて、 [ModuleType](../windows/moduletype-enumeration.md)テンプレート パラメーターを作成するとき、[モジュール](../windows/module-class.md)オブジェクト。 このポリシーを上書きするには、指定、`FactoryCacheFlags`ファクトリ オブジェクトを作成するときの値します。  
  
|||  
|-|-|  
|`FactoryCacheDefault`|キャッシュ ポリシー、`Module`オブジェクトを使用します。|  
|`FactoryCacheEnabled`|関係なくファクトリがキャッシュされるように、`ModuleType`の作成に使用するテンプレート パラメーター、`Module`オブジェクト。|  
|`FactoryCacheDisabled`|工場出荷時に関係なくキャッシュを無効にします`ModuleType`の作成に使用するテンプレート パラメーター、`Module`オブジェクト。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)