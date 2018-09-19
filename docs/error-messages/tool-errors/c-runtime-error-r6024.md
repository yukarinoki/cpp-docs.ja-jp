---
title: C ランタイム エラー R6024 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6024
dev_langs:
- C++
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10b258b12bb1ad7e47a7b126b8fd503814186645
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041598"
---
# <a name="c-runtime-error-r6024"></a>C ランタイム エラー R6024

_onexit atexit/テーブルの領域が不足

> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは通常、非常に低いメモリ条件では、まれには、プログラムのバグによってまたは使用する Visual C ライブラリの破損によってに発生します。
>
>  このエラーを解決するには、次の手順を試してみます。
>
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放するため、コンピューターを再起動します。
> -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **修復または Microsoft Visual C Redistributable のすべてのコピーを再インストールします。
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

使用可能なメモリがないために、このエラーが発生します、`_onexit`または`atexit`関数。 このエラーは、メモリ不足の状態によって発生します。 ユーザー データを保存し、クリーンなアプリを実行するを支援するアプリの起動時に事前割り当てのバッファーがメモリ不足の状態で終了を検討することがあります。