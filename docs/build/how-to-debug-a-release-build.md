---
description: '詳細情報: 方法:リリース ビルドをデバッグする'
title: '方法: リリース ビルドをデバッグする'
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
ms.openlocfilehash: bbe70a534a9d953ea1b739dba3a32296c7893930
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162704"
---
# <a name="how-to-debug-a-release-build"></a>方法: リリース ビルドをデバッグする

アプリケーションのリリース ビルドをデバッグできます。

### <a name="to-debug-a-release-build"></a>リリース ビルドをデバッグするには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** ノードをクリックします。 **[デバッグ情報の形式]** を [[C7 互換 (/Z7)]](reference/z7-zi-zi-debug-information-format.md) または **[プログラム データベース (/Zi)]** に設定します。

1. **[リンカー]** を展開し、 **[全般]** ノードをクリックします。 **[インクリメンタル リンクを有効にする]** を [[いいえ (/INCREMENTAL:NO)]](reference/incremental-link-incrementally.md) に変更します。

1. **[デバッグ]** ノードを選択します。 **[デバッグ情報を作成]** を [[はい (/DEBUG)]](reference/debug-generate-debug-info.md) に設定します。

1. **[最適化]** ノードを選択します。 **[参照]** を [[/OPT:REF]](reference/opt-optimizations.md) に設定し、 **[COMDAT の圧縮]** を [[/OPT:ICF]](reference/opt-optimizations.md) に設定します。

1. これでリリース ビルド アプリケーションをデバッグできます。 問題を見つけるには、失敗の発生箇所が見つかるまでコードをステップ実行し (あるいは、Just-In-Time デバッグを使用し)、間違ったパラメーターまたはコードを判断します。

   あるアプリケーションがデバッグ ビルドで動作するが、リリース ビルドで失敗する場合、コンパイラ最適化の 1 つがソース コードで欠陥をさらしている可能性があります。 問題を分離するため、問題を引き起こしているファイルと最適化が見つかるまで、ソース コード ファイルごとに選択した最適化を無効にします。 (このプロセスを早めるには、ファイルを 2 つのグループに分割し、1 つのグループで最適化を無効にし、グループ内で問題が見つかったら、問題のあるファイルが分離されるまで、分割を続けます)

   [/RTC](reference/rtc-run-time-error-checks.md) を使用し、デバッグ ビルドでこのようなバグを見つけてみてください。

   詳しくは、「[コードの最適化](optimizing-your-code.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[リリース ビルドの問題の解決](fixing-release-build-problems.md)
