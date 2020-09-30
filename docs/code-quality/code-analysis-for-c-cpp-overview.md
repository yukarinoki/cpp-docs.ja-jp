---
title: C/C++ のコード分析の概要
ms.date: 04/28/2018
ms.topic: conceptual
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
ms.openlocfilehash: f128c9722138f453c72ca97b09cc1a69a737dbf6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504193"
---
# <a name="code-analysis-for-cc-overview"></a>C/C++ のコード分析の概要

C/c + + コード分析ツールは、C/c + + ソースコードで発生する可能性のある欠陥に関する情報を提供します。 このツールで報告される一般的なコーディング エラーとして、バッファー オーバーラン、初期化されていないメモリ、Null ポインターの逆参照、メモリ リーク、リソース リークなどがあります。 このツールでは、 [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)に対してチェックを実行することもできます。

## <a name="ide-integrated-development-environment-integration"></a>IDE (統合開発環境) の統合

コード分析ツールは、Visual Studio IDE 内で完全に統合されています。

ビルド プロセス中は、ソース コードに対して生成された警告がエラー一覧に表示されます。 警告の原因となったソース コードに移動して、問題の原因と考えられる解決策に関する追加情報を表示できます。

## <a name="command-line-support"></a>コマンドラインのサポート

次の例に示すように、コマンドラインから分析ツールを使用することもできます。

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 バージョン15.7 以降:** CMake を含む任意のビルドシステムを使用して、コマンドラインからツールを実行できます。

## <a name="pragma-support"></a>#pragma サポート

このディレクティブを使用すると、警告を `#pragma` エラーとして扱うことができます。警告を有効または無効にしたり、個々のコード行の警告を非表示にしたりすることができます。 詳細については、「[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。

## <a name="annotation-support"></a>注釈のサポート

注釈によってコード分析の精度が向上します。 注釈には、関数のパラメーターと戻り値の型について、事前および事後の状態に関する追加情報を指定します。 詳細については、「 [SAL 注釈を使用して C/c + + コードの欠陥を減らす](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)」を参照してください。

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>チェックイン ポリシーの一部としての分析ツールの実行

チェックインされるすべてのソース コードが、特定のポリシーを満たしていることが必要な場合があります。 具体的には、最新のローカル ビルドのステップとして分析が実行されたことを確認する必要があります。 コード分析のチェックインポリシーを有効にする方法の詳細については、「 [コード分析のチェックインポリシーの作成と使用](/visualstudio/code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies)」を参照してください。

## <a name="team-build-integration"></a>チームビルドの統合

ビルドシステムの統合された機能を使用して、Azure DevOps のビルドプロセスの手順としてコード分析ツールを実行できます。 詳細については、「[Azure Pipelines](/azure/devops/pipelines/index)」を参照してください。

## <a name="see-also"></a>関連項目

- [クイックスタート: C/C++ のコード分析](quick-start-code-analysis-for-c-cpp.md)
- [チュートリアル: C/c + + コード分析による欠陥の分析](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/c + + のコード分析の警告](code-analysis-for-c-cpp-warnings.md)
- [C++ Core ガイドライン チェッカーの使用](using-the-cpp-core-guidelines-checkers.md)
- [C++ Core Guidelines チェッカーリファレンス](code-analysis-for-cpp-corecheck.md)
- [規則セットを使用して、実行する C++ 規則を指定する](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [コード分析ツールを使用したドライバー品質の分析](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [ドライバーのコード分析の警告](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
