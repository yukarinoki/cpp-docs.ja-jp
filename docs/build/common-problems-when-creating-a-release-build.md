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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328860"
---
# <a name="common-problems-when-creating-a-release-build"></a>リリース ビルド作成時によくある問題

開発時には、通常、プロジェクトのデバッグ ビルドを使用してビルドとテストを行います。 その後、リリース ビルド用にアプリケーションをビルドすると、アクセス違反が発生する場合があります。

次の一覧は、デバッグとリリース (非デバッグ) ビルドの主な相違点を示しています。 他にも違いがありますが、アプリケーションがデバッグ ビルドで動作するのにリリース ビルドで失敗する原因となるような主な相違点は次のとおりです。

- [ヒープ レイアウト](#_core_heap_layout)

- [コンパイル](#_core_compilation)

- [ポインターのサポート](#_core_pointer_support)

- [最適化](#_core_optimizations)

デバッグ ビルドでリリース ビルド エラーをキャッチする方法の詳細については、[/GZ (デバッグ ビルドでのリリース ビルド エラーのキャッチ)](reference/gz-enable-stack-frame-run-time-error-checking.md) コンパイラ オプションを確認してください。

## <a name="heap-layout"></a><a name="_core_heap_layout"></a> ヒープ レイアウト

ヒープ レイアウトは、アプリケーションがデバッグでは動作するがリリースでは動作しない場合の明らかな問題の約 90% で、その原因になります。

デバッグ用にプロジェクトをビルドするときは、デバッグ メモリ アロケーターを使用しています。 これは、すべてのメモリ割り当ての周囲にガードバイトが配置されていることを意味します。 これらのガードバイトにより、メモリの上書きが検出されます。 ヒープ レイアウトはリリースとデバッグのバージョンで異なるため、メモリの上書きによってデバッグ ビルドでは問題が発生しないかもしれませんが、リリース ビルドには致命的な影響が生じる可能性があります。

詳細については、「[メモリ上書きを確認する](checking-for-memory-overwrites.md)」と、[デバッグ ビルドを使用したメモリ上書きのチェック](using-the-debug-build-to-check-for-memory-overwrite.md)に関する記事を参照してください。

## <a name="compilation"></a><a name="_core_compilation"></a> コンパイル

MFC マクロの多くと MFC 実装の大部分は、リリース用にビルドするときに変更されます。 特に、ASSERT マクロはリリース ビルドでは何も評価されないので、ASSERT で見つかったコードは実行されません。 詳細については、[ASSERT ステートメントの調査](using-verify-instead-of-assert.md)に関する記事を参照してください。

一部の関数は、リリース ビルドの高速化のためにインライン化されます。 最適化は、一般にリリース ビルドで有効になっています。 別のメモリ アロケーターも使用されています。

## <a name="pointer-support"></a><a name="_core_pointer_support"></a> ポインターのサポート

デバッグ情報がないと、アプリケーションから埋め込みが削除されます。 リリース ビルドでは、無効なポインターがデバッグ情報を指すのではなく、初期化されていないメモリを指す可能性がより高くなります。

## <a name="optimizations"></a><a name="_core_optimizations"></a> 最適化

コードの特定のセグメントの性質によっては、最適化コンパイラによって予期しないコードが生成されることがあります。 これは、リリース ビルドの問題の原因として最も可能性が低いですが、時々発生します。 解決策については、「[コードの最適化](optimizing-your-code.md)」を参照してください。

## <a name="see-also"></a>関連項目

[リリース ビルド](release-builds.md)<br/>
[リリース ビルドの問題の解決](fixing-release-build-problems.md)
