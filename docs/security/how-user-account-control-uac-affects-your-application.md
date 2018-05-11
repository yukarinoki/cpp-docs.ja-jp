---
title: ユーザー アカウント制御 (UAC) が、アプリケーションに与える影響 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 020a7a16e38ee40c99a7a5b77c88002e3135bfa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-user-account-control-uac-affects-your-application"></a>ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響
ユーザー アカウント制御 (UAC: User Account Control) は、限られた特権をユーザー アカウントに付与する Windows Vista の機能です。 UAC の詳細については、以下のサイトを参照してください。  
  
-   [Windows Vista ユーザー アカウント制御のステップ バイ ステップ ガイド](http://go.microsoft.com/fwlink/p/?linkid=53781)  
  
-   [開発者のベスト プラクティスと、最低限の特権の環境でアプリケーションのガイドライン](http://go.microsoft.com/fwlink/p/?linkid=82444)  
  
-   [理解して、Windows Vista でのユーザー アカウント制御の構成](http://go.microsoft.com/fwlink/p/?linkid=82445)  
  
## <a name="building-projects-after-enabling-uac"></a>UAC を有効にした後のプロジェクトのビルド  
 UAC を無効にした状態で Windows Vista で Visual C++ プロジェクトをビルドし、後で UAC を有効にする場合は、正しく動作させるためにプロジェクトを消去して、リビルドする必要があります。  
  
## <a name="applications-that-require-administrative-privileges"></a>管理特権を必要とするアプリケーション  
 既定では、Visual C++ リンカーは、実行レベル `asInvoker` でアプリケーションのマニフェストに UAC フラグメントを組み込みます。 正しく実行するためにアプリケーションが管理特権を必要とする場合 (たとえば、アプリケーションがレジストリの HKLM ノードを変更する場合、または Windows ディレクトリなどのディスクの保護領域に書き込みを行う場合)、アプリケーションを変更する必要があります。  
  
 最初のオプションは、実行レベルを変更するマニフェストの UAC フラグメントを変更する*requireAdministrator*です。 これにより、アプリケーションは実行前に管理資格情報を求めてユーザーにプロンプトを表示するようになります。 これを行う方法については、次を参照してください。 [/MANIFESTUAC (マニフェストに UAC 情報)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md)です。  
  
 2 番目のオプションがないを指定してマニフェストに UAC フラグメントを埋め込むには、 **/MANIFESTUAC:NO**リンカー オプション。 この場合、アプリケーションは仮想実行されます。 レジストリまたはファイル システムに変更を加えた場合、その変更はすべてアプリケーションの終了後に失われます。  
  
 UAC が有効な場合と無効な場合、またアプリケーションに UAC マニフェストがある場合とない場合のアプリケーションの動作の違いを次のフローチャートで説明します。  
  
 ![Windows Vista ローダーの動作](media/uacflowchart.png "UACflowchart")  
  
## <a name="see-also"></a>関連項目  
 [セキュリティ推奨事項](security-best-practices-for-cpp.md)