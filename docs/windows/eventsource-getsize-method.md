---
title: Eventsource::getsize メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::GetSize
dev_langs:
- C++
helpviewer_keywords:
- GetSize method
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60c52c711c85caa64c289937f39fe50ec18e1839
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33887001"
---
# <a name="eventsourcegetsize-method"></a>EventSource::GetSize メソッド
現在の EventSource オブジェクトに関連付けられているイベント ハンドラーの数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>戻り値  
 内のイベント ハンドラーの数[targets _](../windows/eventsource-targets-data-member.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [EventSource クラス](../windows/eventsource-class.md)