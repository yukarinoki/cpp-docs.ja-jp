---
title: エラー フック |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be598a77ca48eeee03360a3b598b0567abc6ee4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371786"
---
# <a name="failure-hooks"></a>エラー フック
エラー フックと同じ方法で有効になっている、[通知フック](../../build/reference/notification-hooks.md)です。 フック ルーチンの必要性を処理できるように、適切な値を返すことが続行する (HINSTANCE か FARPROC) または 0 で、例外をスローすることを示します。  
  
 ユーザー定義関数を参照するポインター変数は。  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 **DelayLoadInfo**から値を含むエラーの正確なレポートに必要な適切なデータが構造に含まれる`GetLastError`です。  
  
 場合は、通知は**dliFailLoadLib**、フック関数が返すことができます。  
  
-   エラーを処理できない場合は 0。  
  
-   HMODULE は、エラー フックが修正される問題と、ライブラリ自体をロードします。  
  
 場合は、通知は**dliFailGetProc**、フック関数が返すことができます。  
  
-   エラーを処理できない場合は 0。  
  
-   有効な proc アドレス (インポート関数アドレス) 場合は、障害のフックは、自体アドレスの取得に成功しました。  
  
## <a name="see-also"></a>関連項目  
 [エラー処理と通知](../../build/reference/error-handling-and-notification.md)