---
title: リリース ビルド作成時によくある問題
ms.date: 11/04/2016
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
ms.openlocfilehash: 9bd1cafe40417872d42f2e9e1427e5f2eccad7a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328860"
---
# <a name="common-problems-when-creating-a-release-build"></a>リリース ビルド作成時によくある問題

開発中は、通常、プロジェクトのデバッグ ビルドを使用してビルドおよびテストを行います。 その後、リリース ビルド用にアプリケーションをビルドすると、アクセス違反が発生する可能性があります。

以下のリストは、デバッグ ビルドとリリース (非デバッグ) ビルドの主な違いを示しています。 他にも違いがありますが、デバッグ ビルドで動作する場合にアプリケーションがリリース ビルドで失敗する主な違いは次のとおりです。

- [ヒープレイアウト](#_core_heap_layout)

- [コンパイル](#_core_compilation)

- [ポインタのサポート](#_core_pointer_support)

- [最適化](#_core_optimizations)

デバッグ ビルドでリリース ビルド エラーをキャッチする方法については[、/GZ (デバッグ ビルドで](reference/gz-enable-stack-frame-run-time-error-checking.md)のリリース ビルド エラーのキャッチ) コンパイラ オプションを参照してください。

## <a name="heap-layout"></a><a name="_core_heap_layout"></a>ヒープレイアウト

ヒープ レイアウトは、アプリケーションがデバッグで動作するがリリースでは行わない場合に、明らかな問題の約 90% の原因になります。

デバッグ用にプロジェクトをビルドする場合は、デバッグ メモリ アロケーターを使用しています。 つまり、すべてのメモリ割り当てでは、ガード バイトが配置されます。 これらのガード バイトは、メモリの上書きを検出します。 ヒープ レイアウトはリリース バージョンとデバッグ バージョンによって異なるため、メモリの上書きによってデバッグ ビルドで問題が発生する可能性はありませんが、リリース ビルドでは致命的な影響を及ぼす可能性があります。

詳細については、「[メモリ上書きのチェック](checking-for-memory-overwrites.md)」および[「デバッグ ビルドを使用してメモリの上書きをチェックする](using-the-debug-build-to-check-for-memory-overwrite.md)」を参照してください。

## <a name="compilation"></a><a name="_core_compilation"></a>コンパイル

MFC マクロの多くと MFC 実装の多くは、リリース用にビルドすると変更されます。 特に、ASSERT マクロはリリース ビルドでは何も評価されないので、ASSERT で見つかったコードは実行されません。 詳細については、「 [ASSERT ステートメントの調査](using-verify-instead-of-assert.md)」を参照してください。

一部の関数は、リリース ビルドの速度を向上するためにインライン化されます。 通常、リリース ビルドでは最適化が有効になります。 別のメモリアロケーターも使用されています。

## <a name="pointer-support"></a><a name="_core_pointer_support"></a>ポインタのサポート

デバッグ情報が不足していると、アプリケーションのパディングが削除されます。 リリース ビルドでは、迷子のポインターは、デバッグ情報を指す代わりに、初期化されていないメモリを指す可能性が高くなります。

## <a name="optimizations"></a><a name="_core_optimizations"></a>最適化

特定のコード セグメントの性質によっては、最適化コンパイラによって予期しないコードが生成される場合があります。 これはリリース ビルドの問題の最も可能性の低い原因ですが、発生する場合もあります。 解決策については、「[コードの最適化](optimizing-your-code.md)」を参照してください。

## <a name="see-also"></a>関連項目

[リリース ビルド](release-builds.md)<br/>
[リリース ビルドの問題の解決](fixing-release-build-problems.md)
