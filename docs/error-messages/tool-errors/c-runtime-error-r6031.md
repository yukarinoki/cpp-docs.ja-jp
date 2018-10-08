---
title: C ランタイム エラー R6031 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6031
dev_langs:
- C++
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a0ccd608baa2765ae355a16b9a71afbf3695d8f
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48859784"
---
# <a name="c-runtime-error-r6031"></a>C ランタイム エラー R6031

CRT を複数回初期化しようとしてください。 これは、アプリケーションにバグを示します。

> [!NOTE]
> アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 これが発生するバグまたはアドオンまたは、アプリが使用する拡張機能のバグによって、アプリで。
>
> このエラーを解決するには、次の手順を試してみます。
>
> - 使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> - 使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を削除するには、修復またはアプリで使用されるアドオンや拡張機能のプログラムを再インストールします。
> - 確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> - アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

この診断は、ローダー ロック中に MSIL 命令が実行されたことを示します。 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)します。