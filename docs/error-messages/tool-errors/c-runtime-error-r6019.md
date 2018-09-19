---
title: C ランタイム エラー R6019 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6019
dev_langs:
- C++
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95bc763ab39df16c1cfc1b05689560edecf70570
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093306"
---
# <a name="c-runtime-error-r6019"></a>C ランタイム エラー R6019

コンソールのデバイスを開けません

> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、コンソールにアクセスしようとしたが、十分なアクセス許可がないためです。 このエラーは、いくつかの原因が考えられますが、管理者は、プログラムを実行する必要がありますか、プログラムでバグがあるため、これは通常します。
>
>  このエラーを解決するには、次の手順を試してみます。
>
>  -   管理者としてプログラムを実行します。
> -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

このエラーは、アプリ、コンソール関数と呼ばれますが、オペレーティング システムでは、コンソールへのアクセスを付与しなかったために発生します。 除くデバッグ モードでコンソールの機能は通常できません Microsoft Store アプリ。 アプリを実行する管理者特権を必要とする場合は、既定では管理者として実行するインストールを確認します。