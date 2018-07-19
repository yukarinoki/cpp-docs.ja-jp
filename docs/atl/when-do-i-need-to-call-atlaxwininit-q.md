---
title: ときになを呼び出す必要があるのですか。 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9aa1dd14ccae555d4ab9acbbac15e9b66cafe6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360274"
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>ときになを呼び出す必要があるのですか。

[な](reference/composite-control-global-functions.md#atlaxwininit)登録、 **"AtlAxWin80"** ウィンドウ (さらに、いくつかのカスタム ウィンドウ メッセージには) クラスのため、ホスト ウィンドウを作成しようとする前に、この関数を呼び出す必要があります。 ただし、常にする必要はありません Api (およびそれらを使用するクラス) をホストから明示的に、この関数の呼び出しを多くの場合、この関数を呼び出します。 この関数を複数回呼び出す害はありません。 である必要があります。  
  
## <a name="see-also"></a>関連項目  
 AtlAxWinTerm を呼び出す必要が場合     
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)
