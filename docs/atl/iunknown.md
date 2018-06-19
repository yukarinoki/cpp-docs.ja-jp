---
title: IUnknown |Microsoft ドキュメント
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
ms.openlocfilehash: c02018ee3cefb1b98c2df850d44578cf3a092c64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355840"
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)は、その他のすべての COM インターフェイスの基本インターフェイスです。  このインターフェイスは、3 つのメソッドを定義します。 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)、 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、および[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)です。 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)ユーザーは、使用インターフェイスに別のインターフェイスへのポインターのオブジェクトを確認してください。 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)インターフェイスの参照カウントを実装します。  
  
## <a name="see-also"></a>関連項目  
 [COM の概要](../atl/introduction-to-com.md)   
 [IUnknown とインターフェイスの継承](http://msdn.microsoft.com/library/windows/desktop/ms692713)

