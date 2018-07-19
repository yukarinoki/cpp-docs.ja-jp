---
title: IUnknown |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d832d2978bf9db82b290d77b236fea1c9bcada58
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953043"
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)は他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、3 つのメソッドを定義します。 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)、 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、および[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)します。 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)インターフェイス ユーザーに対して、別のインターフェイスへのポインター オブジェクトを要求できます。 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)インターフェイスの参照カウントを実装します。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [IUnknown とインターフェイスの継承](http://msdn.microsoft.com/library/windows/desktop/ms692713)

