---
title: Asyncbase::oncancel メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs:
- C++
helpviewer_keywords:
- OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 346cb4049f0833bdbc950b6806177321d107db28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380735"
---
# <a name="asyncbaseoncancel-method"></a>AsyncBase::OnCancel メソッド

派生クラスでオーバーライドされると、非同期操作をキャンセルします。

## <a name="syntax"></a>構文

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)<br/>
[AsyncBase::Cancel メソッド](../windows/asyncbase-cancel-method.md)