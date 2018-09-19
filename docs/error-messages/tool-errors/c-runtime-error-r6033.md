---
title: C ランタイム エラー R6033 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6033
dev_langs:
- C++
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb107dcd2bd044ad6fb933869319bb7afd5aab72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049801"
---
# <a name="c-runtime-error-r6033"></a>C ランタイム エラー R6033

ネイティブ コードの初期化中にこのアセンブリの MSIL コードを使用しようとしてください。 これは、アプリケーションにバグを示します。 MSIL でコンパイルを呼び出した結果ではほとんどの場合 (/clr) ネイティブのコンス トラクターからまたは Dll からエクスポートされた関数。

> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、またはアドインまたは使用する拡張機能のバグによって、アプリのバグによって発生することができます。
>
>  このエラーを解決するには、次の手順を試してみます。
>
>  -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を削除、修復の拡張またはアドインを再インストールします。
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

この診断は、ローダー ロック中に MSIL 命令が実行されたことを示します。 これは、ネイティブ C++/clr フラグを使用してコンパイルした場合に発生することができます。 のみを含むマネージ コード モジュールを/clr フラグを使用します。 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)します。