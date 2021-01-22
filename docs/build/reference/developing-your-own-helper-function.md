---
description: 独自の遅延読み込みヘルパー関数の開発に関する詳細情報
title: 独自の遅延読み込みヘルパー関数を開発する
ms.date: 01/19/2021
helpviewer_keywords:
- helper functions
ms.openlocfilehash: 2845a426023ed8b5e2bcfb0056c9be6b829dd23a
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667430"
---
# <a name="develop-your-own-delay-load-helper-function"></a>独自の遅延読み込みヘルパー関数を開発する

独自のバージョンの遅延読み込みヘルパールーチンを用意することもできます。 独自のルーチンでは、DLL またはインポートの名前に基づいて特定の処理を行うことができます。 独自のコードを挿入するには、次の2つの方法があります。指定されたコードに基づいて独自のヘルパー関数をコーディングすることができます。 または、指定されたヘルパーをフックして、 [通知フック](notification-hooks.md)を使用して独自の関数を呼び出します。

## <a name="code-your-own-helper"></a>独自のヘルパーをコーディングする

独自のヘルパールーチンを作成するのは簡単です。 既存のコードを新しい関数のガイドとして使用することができます。 関数では、既存のヘルパーと同じ呼び出し規約を使用する必要があります。 また、リンカーによって生成されたサンクに戻る場合は、適切な関数ポインターを返す必要があります。 コードを作成したら、呼び出しを満たすか、呼び出しを取得することができます。

## <a name="use-the-start-processing-notification-hook"></a>処理開始通知フックを使用する

通知の既定のヘルパーと同じ値を受け取るユーザー指定の通知フック関数への新しいポインターを提供するのが最も簡単な方法です `dliStartProcessing` 。 その時点で、フック関数は実質的に新しいヘルパー関数になります。既定のヘルパーに正常に戻ると、既定のヘルパーでの後続の処理がすべてバイパスされるためです。

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
