---
title: '方法: リリース ビルドをデバッグ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e733375f01d4b2b8ec7090f7f70ad1ec5280cd9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374480"
---
# <a name="how-to-debug-a-release-build"></a>方法 : リリース ビルドをデバッグする
アプリケーションのリリース ビルドをデバッグすることができます。  
  
### <a name="to-debug-a-release-build"></a>リリース ビルドをデバッグするには  
  
1.  開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、 **C/C++** ノード。 設定**デバッグ情報の形式**に[C7 互換 (/Z7)](../../build/reference/z7-zi-zi-debug-information-format.md)または**プログラム データベース (/Zi)** です。  
  
3.  展開**リンカー**  をクリックし、**全般**ノード。 設定**インクリメンタル リンクを有効にする**に[いいえ (//INCREMENTAL:NO)](../../build/reference/incremental-link-incrementally.md)です。  
  
4.  選択、**デバッグ**ノード。 設定**デバッグ情報の生成**に[はい (/debug)](../../build/reference/debug-generate-debug-info.md)です。  
  
5.  選択、**最適化**ノード。 設定**参照**に[/opt:ref による](../../build/reference/opt-optimizations.md)と**COMDAT の圧縮を有効にする**に[/OPT:ICF](../../build/reference/opt-optimizations.md)です。  
  
6.  リリース ビルドのアプリケーションをデバッグできます。 障害が発生したが見つかるまで、問題、ステップ実行、コード (または使用ジャスト イン タイムのデバッグ) を検索し、不正確なパラメーターまたはコードを確認しています。  
  
     アプリケーション デバッグ ビルドでは動作では、リリース ビルドに失敗した場合は、コンパイラの最適化のいずれかの可能性があるを公開する、ソース コードの欠陥です。 問題を特定するには、ファイルと、問題の原因となった、最適化が見つかるまで、各ソース コード ファイルの選択の最適化を無効にします。 (処理の時間を短縮するには、ファイルを 2 つのグループに分割、1 つのグループでの最適化を無効にするコンティニュできます、グループ内に問題が見つかったときに除算問題のファイルを特定できます。)  
  
     使用することができます[/RTC](../../build/reference/rtc-run-time-error-checks.md)デバッグ ビルドでこのようなバグを公開しようとします。  
  
     詳細については、次を参照してください。[コードの最適化](../../build/reference/optimizing-your-code.md)です。  
  
## <a name="see-also"></a>関連項目  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)