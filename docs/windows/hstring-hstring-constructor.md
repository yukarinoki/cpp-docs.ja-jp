---
title: Hstring::hstring コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96b77ec87e3219206d353f56293fc201c46f5d7e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568772"
---
# <a name="hstringhstring-constructor"></a>HString::HString コンストラクター
新しいインスタンスを初期化、 **HString**クラス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hstr*  
 HSTRING ハンドルの場合。  
  
 *other*  
 既存の**HString**オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 最初のコンス トラクターによって初期化新しい**HString**オブジェクトが空です。  
  
 2 番目のコンス トラクターによって初期化、新しい**HString**オブジェクト、既存の値から*他*パラメーター、し、その後破棄、*他*パラメーター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)