---
title: C ランタイム エラー R6024 |Microsoft ドキュメント
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
ms.openlocfilehash: bcdfee9da378415afe0b88fe6eed18ec8f570d4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302712"
---
# <a name="c-runtime-error-r6024"></a>C ランタイム エラー R6024
_onexit/atexit テーブル領域が足りません。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは通常、非常に低いメモリ条件では、またはまれには、プログラムのバグまたはによって使用されている Visual C ライブラリの破損に発生します。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放する、コンピューターを再起動します。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復またはプログラムを再インストールします。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復または、Microsoft Visual C 再頒布可能のすべてのコピーを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 使用可能なメモリがないために、このエラーが発生した、`_onexit`または`atexit`関数。 このエラーは、メモリ不足の状況で発生します。 ユーザー データの保存とクリーン アプリの実行を支援するアプリの起動時に割り当て済みのバッファーがメモリの少ない状況で終了を検討する可能性があります。