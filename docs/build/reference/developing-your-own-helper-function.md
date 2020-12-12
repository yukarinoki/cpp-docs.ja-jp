---
description: 詳細については、独自のヘルパー関数の開発に関するページを参照してください。
title: 独自のヘルパー関数の作成
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
ms.openlocfilehash: da536d13da9a596c5667c3fa84311b73e66d71ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201457"
---
# <a name="developing-your-own-helper-function"></a>独自のヘルパー関数の作成

独自のバージョンのルーチンを提供して、DLL またはインポートの名前に基づいて特定の処理を行うことができます。 これを行う方法は2つあります。独自にコーディングする方法、指定したコードに基づいて記述する方法、または前に説明した通知フックを使用して指定されたバージョンをフックする方法です。

## <a name="code-your-own"></a>独自のコードを作成する

これは、指定されたコードを新しいもののガイドラインとして基本的に使用できるため、非常に簡単です。 もちろん、呼び出し規約に従う必要があり、リンカーによって生成されたサンクに戻る場合は、適切な関数ポインターを返す必要があります。 コード内では、呼び出しを満たすために、または呼び出しを取得するために、必要な操作をほとんど行うことができます。

## <a name="use-the-start-processing-notification-hook"></a>処理開始通知フックを使用する

通常は、notification dliStartProcessing の既定のヘルパーと同じ値を受け取るユーザー指定の通知フック関数への新しいポインターを提供するのが最も簡単です。 その時点で、フック関数は実質的に新しいヘルパー関数になります。既定のヘルパーに正常に戻ると、既定のヘルパーでの後続の処理がすべてバイパスされるためです。

## <a name="see-also"></a>関連項目

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
