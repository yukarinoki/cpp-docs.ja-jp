---
title: '方法: リリース ビルドをデバッグ |Microsoft Docs'
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
ms.openlocfilehash: 2dcafe151edf907521c2db49b4ffacca38593e9b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723906"
---
# <a name="how-to-debug-a-release-build"></a>方法 : リリース ビルドをデバッグする

アプリケーションのリリース ビルドをデバッグすることができます。

### <a name="to-debug-a-release-build"></a>リリース ビルドをデバッグするには

1. 開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. をクリックして、 **C/C++** ノード。 設定**デバッグ情報の形式**に[C7 互換 (/Z7)](../../build/reference/z7-zi-zi-debug-information-format.md)または**プログラム データベース (/Zi)** します。

1. 展開**リンカー**  をクリックし、**全般**ノード。 設定**インクリメンタル リンクを有効にする**に[いいえ (//INCREMENTAL:NO)](../../build/reference/incremental-link-incrementally.md)します。

1. 選択、**デバッグ**ノード。 設定**デバッグ情報の生成**に[はい (/debug)](../../build/reference/debug-generate-debug-info.md)します。

1. 選択、**最適化**ノード。 設定**参照**に[/OPT:REF](../../build/reference/opt-optimizations.md)と**COMDAT の圧縮を有効にする**に[/OPT:ICF](../../build/reference/opt-optimizations.md)します。

1. リリース ビルドのアプリケーションをデバッグできます。 障害が発生すると表示されるまでのステップ実行、コード (またはジャスト イン タイムを使用してデバッグ)、問題を検索し、正しくないパラメーターまたはコードを確認します。

   アプリケーションは、デバッグ ビルドでは動作が、リリース ビルドでできない場合、ソース コードの欠陥を公開コンパイラの最適化の 1 つに可能性があります。 問題を特定するには、ファイルと、問題の原因となっている最適化が見つかるまで、各ソース コード ファイルの選択の最適化を無効にします。 (プロセスの時間を短縮するには、ファイルを 2 つのグループに分割、1 つのグループでの最適化を無効にするコンティニュできますグループに問題が見つかったときに問題のファイルが特定されるまでに分割します。)

   使用することができます[/RTC](../../build/reference/rtc-run-time-error-checks.md)デバッグ ビルドでは、このようなバグを公開しようとします。

   詳細については、次を参照してください。[コードの最適化](../../build/reference/optimizing-your-code.md)します。

## <a name="see-also"></a>関連項目

[リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)