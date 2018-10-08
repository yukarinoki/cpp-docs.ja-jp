---
title: C ランタイム エラー R6032 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6032
dev_langs:
- C++
helpviewer_keywords:
- R6032
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dc68723e07d7ef8c3b9d9f6ad913466b7ff27e4
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48859719"
---
# <a name="c-runtime-error-r6032"></a>C ランタイム エラー R6032

ロケール情報領域が足りません。

> [!NOTE]
> アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは、いくつかの理由がありますが、多くの場合、またはプログラムのバグによって、非常に低いメモリ条件によって原因が。
>
> このエラーを解決するには、次の手順を試してみます。
>
> - その他の実行中のアプリケーションを閉じるか、メモリを解放するため、コンピューターを再起動します。
> - 使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> - 確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> - アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

ランタイムは、ロケールに依存する関数への呼び出しを処理できるように、各スレッドのロケールに関する情報を保持します。 詳細については、メモリの割り当てに失敗した場合、ランタイムが依存しているため、基本的な機能の多くを行うことができません。