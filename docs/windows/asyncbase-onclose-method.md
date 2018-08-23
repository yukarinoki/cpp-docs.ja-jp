---
title: Asyncbase::onclose メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnClose
dev_langs:
- C++
helpviewer_keywords:
- OnClose method
ms.assetid: 96766450-c262-4611-8534-7d190b799142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fd6bd03b1e5aa3f690d93a5c51cc6664e0547c2e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597350"
---
# <a name="asyncbaseonclose-method"></a>AsyncBase::OnClose メソッド

派生クラスでオーバーライドされると、非同期操作を終了します。

## <a name="syntax"></a>構文

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)  
[AsyncBase::Close メソッド](../windows/asyncbase-close-method.md)