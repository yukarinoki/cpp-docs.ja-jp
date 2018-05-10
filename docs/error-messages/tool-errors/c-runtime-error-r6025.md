---
title: C ランタイム エラー R6025 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6025
dev_langs:
- C++
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abdbdbf918462dfb83eff07190c32af1f1b3d015
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="c-runtime-error-r6025"></a>C ランタイム エラー R6025
純粋仮想関数呼び出し  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーの最も一般的な理由は、アプリ、または破損したインストールでバグです。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 オブジェクトがインスタンス化されていない純粋仮想関数呼び出しを処理します。  
  
 このエラーは、抽象基本クラス。 これは、派生クラスの型へのキャストによって作成されますが、基底クラスへのポインターでは実際には、ポインターを介して仮想関数を呼び出すことによって発生します。 これからキャストする場合に発生することができます、 **void\*** クラスへのポインターにときに、 **void\*** 基底クラスの構築時に作成されました。  
  
 詳細については、次を参照してください。、 [Microsoft サポート](http://go.microsoft.com/fwlink/p/?linkid=75220)web サイトです。