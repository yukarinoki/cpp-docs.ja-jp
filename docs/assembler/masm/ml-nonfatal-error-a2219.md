---
description: '詳細情報: ML の致命的でないエラー A2219'
title: ML の致命的でないエラー A2219
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: 3b9fd2f397f702a32784cd696bcbc3a72f35cf95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128311"
---
# <a name="ml-nonfatal-error-a2219"></a>ML の致命的でないエラー A2219

> アンワインドコードのオフセットのアラインメントが正しくありません

## <a name="remarks"></a>解説

[ &period; Allocstack](dot-allocstack.md)と[ &period; SAVEREG](dot-savereg.md)のオペランドは8の倍数である必要があります。  [ &period; SAVEXMM128](dot-savexmm128.md)と[ &period; setframe](dot-setframe.md)のオペランドは16の倍数である必要があります。

## <a name="see-also"></a>関連項目

[ML エラーメッセージ](ml-error-messages.md)
