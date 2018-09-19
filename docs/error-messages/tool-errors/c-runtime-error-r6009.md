---
title: C ランタイム エラー R6009 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6009
dev_langs:
- C++
helpviewer_keywords:
- R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0deafa72a427543c0d885401a1d4192d61a6db65
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069041"
---
# <a name="c-runtime-error-r6009"></a>C ランタイム エラー R6009

環境の容量が不十分

> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは、いくつかの理由がありますが、多くの場合、原因が、非常に低いメモリ条件、環境変数、またはプログラムのバグによって使用されてメモリが多すぎます。
>
>  このエラーを解決するには、次の手順を試してみます。
>
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放するため、コンピューターを再起動します。
> -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

プログラムを読み込むための十分なメモリが十分なメモリを作成する、 **envp**配列。  これは、非常に低いメモリ条件によって、または非常に大規模な環境変数を使用して発生することができます。 次の解決策のいずれかを検討してください。

- プログラムに使用可能なメモリの量を増やします。

- コマンドライン引数のサイズと数を減らします。

- 環境のサイズを小さくには、不要な変数を削除します。