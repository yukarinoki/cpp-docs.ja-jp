---
title: 独自のヘルパー関数の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6b8e397fecc8f14140cd7c86217421d5aa1a749
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371399"
---
# <a name="developing-your-own-helper-function"></a>独自のヘルパー関数の作成
DLL またはインポートの名前に基づく特定の処理を実行するルーチンのバージョンを独自に提供することがあります。 これを 2 つの方法はあります。 可能性のある、指定されたコードに基づくのコーディング独自、または以前に詳細な通知フックを使用して指定されたバージョンにフックするだけでします。  
  
 独自のコードします。  
 これは、設定できるので本質的に指定されたコードをガイドラインとして、新しい非常にシンプルです。 もちろん、呼び出し規約に従う必要がありますが、リンカーによって生成されたサンクに返された場合、適切な関数ポインターを返す必要があります。 1 回、コードで非常に希望の呼び出しを満たすか、呼び出しから取得するために実行できます。  
  
 使用して、処理開始通知フック  
 単に通知 dliStartProcessing で既定のヘルパーと同じ値を受信するユーザーが指定した通知用のフック関数への新しいポインターを提供する最も簡単なことが考えられます。 その時点では、フック関数は、実質的に新しいヘルパー関数に、ように正常に返された既定のヘルパーにはそれ以降のすべての既定のヘルパーの処理をバイパスします。  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)