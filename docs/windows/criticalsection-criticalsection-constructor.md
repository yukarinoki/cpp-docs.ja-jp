---
title: Criticalsection::criticalsection コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 866159a4b3cbacae8b7ad09154fb93707fe4baac
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467353"
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection コンストラクター
ミュー テックス オブジェクトに似ていますが、1 つのプロセスのスレッドのみで使用できる同期オブジェクトを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *spincount*  
 クリティカル セクション オブジェクトのスピン カウントします。 既定値は 0 です。  
  
## <a name="remarks"></a>Remarks  
 クリティカル セクションと spincounts の詳細については、次を参照してください。、`InitializeCriticalSectionAndSpinCount`で機能、**同期**Windows API のドキュメントのセクション。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [CriticalSection クラス](../windows/criticalsection-class.md)