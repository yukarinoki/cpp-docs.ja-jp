---
title: C ランタイム エラー R6025 |Microsoft Docs
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
ms.openlocfilehash: b774c5f99387ca4403941d1461593bef8801e5de
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220633"
---
# <a name="c-runtime-error-r6025"></a>C ランタイム エラー R6025
純粋仮想関数呼び出し  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーの最も一般的な理由は、アプリ、または破損したインストールのバグです。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 オブジェクトがインスタンス化されていない純粋仮想関数呼び出しを処理します。  
  
 このエラーは、抽象基本クラスは、派生クラスの型へのキャストによって作成されますが、基底クラスへのポインターでは実際には、ポインターを介して仮想関数を呼び出すことによって発生します。 これからキャストする場合に発生することができます、 **void** <strong>\*</strong>クラスへのポインターにときに、 **void** <strong>\*</strong>されました基底クラスの構築時に作成されます。  
  
 詳細については、次を参照してください。、 [Microsoft サポート](http://go.microsoft.com/fwlink/p/?linkid=75220)web サイト。