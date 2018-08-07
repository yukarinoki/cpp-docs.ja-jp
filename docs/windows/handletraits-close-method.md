---
title: Handletraits::close メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 581c7b8447b800d9a3401cd76f3adc5ada25994d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569831"
---
# <a name="handletraitsclose-method"></a>HANDLETraits::Close メソッド
指定したハンドルを閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *h*  
 ハンドルを閉じます。  
  
## <a name="return-value"></a>戻り値  
 **true**場合処理*h*正常。 それ以外の終了**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [HANDLETraits 構造体](../windows/handletraits-structure.md)