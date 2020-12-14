---
description: 詳細については、「リンカツール Error LNK2038」を参照してください。
title: リンカ ツール エラー LNK2038
ms.date: 12/15/2017
f1_keywords:
- LNK2038
helpviewer_keywords:
- LNK2038
ms.openlocfilehash: 17fa86010b4248b68234292dd909fe50f6379c7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275660"
---
# <a name="linker-tools-error-lnk2038"></a>リンカ ツール エラー LNK2038

> '*name*' に対して不一致が検出されました。値 '*value_1*' は、*ファイル名 .obj* の値 '*value_2*' と一致しません

シンボルの不一致がリンカーによって検出されました。 このエラーは、アプリのさまざまな部分 (ライブラリや、アプリがリンクしているその他のオブジェクトコードなど) が、競合するシンボル定義を使用していることを示します。 [検出不一致](../../preprocessor/detect-mismatch.md)プラグマは、このようなシンボルを定義し、競合する値を検出するために使用されます。

## <a name="possible-causes-and-solutions"></a>考えられる原因と解決策

このエラーは、プロジェクトのオブジェクト ファイルが古い形式のときに発生する可能性があります。 このエラーに対して他のソリューションを実行する前に、オブジェクト ファイルが最新であることを検証するために、クリーン ビルドを実行してください。

Visual Studio は、実行時エラーまたはその他の予測できない動作を発生させる可能性のある互換性のないコードのリンクを防ぐために、次のシンボルを定義します。

- `_MSC_VER` アプリまたはライブラリのビルドに使用される Microsoft C++ コンパイラ (MSVC) のメジャーバージョン番号とマイナーバージョン番号を示します。 1つのバージョンの MSVC を使用してコンパイルされたコードは、メジャーバージョン番号とマイナーバージョン番号が異なるバージョンを使用してコンパイルされたコードと互換性がありません。 詳細については、「 `_MSC_VER` [定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。

   使用しているバージョンの MSVC と互換性のないライブラリにリンクしていて、互換性のあるバージョンのライブラリを取得またはビルドできない場合は、以前のバージョンのコンパイラを使用してプロジェクトをビルドします。プロジェクトの [ **プラットフォームツールセット** ] プロパティを以前のツールセットに変更します。 詳細については、「 [方法: ターゲットフレームワークおよびプラットフォームのツールセットを変更する](../../build/how-to-modify-the-target-framework-and-platform-toolset.md)」を参照してください。

- `_ITERATOR_DEBUG_LEVEL` C++ 標準ライブラリで有効になっているセキュリティ機能とデバッグ機能のレベルを示します。 これらの機能は、特定の C++ 標準ライブラリのオブジェクトの表示を変更できるため、こうしたオブジェクトは、異なるセキュリティ機能とデバッグ機能を使用するオブジェクトと互換性がなくなります。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md)」を参照してください。

- `RuntimeLibrary` アプリまたはライブラリによって使用される C++ 標準ライブラリおよび C ランタイムのバージョンを示します。 C++ 標準ライブラリまたは C ランタイムの 1 種類のバージョンを使用するコードは、異なるバージョンを使用するコードと互換性がありません。 詳細については、「 [/md、/mt、/ld (Run-Time ライブラリを使用する)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。

- `_PPLTASKS_WITH_WINRT`[並列パターンライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)を使用するコードが、 [/ZW](../../build/reference/zw-windows-runtime-compilation.md)コンパイラオプションの別の設定を使用してコンパイルされたオブジェクトにリンクされていることを示します。 (**/ZW** では C++/cx がサポートされています)。またはを使用するコードは、アプリケーションの他の部分で使用されているのと同じ **/ZW** 設定を使用してコンパイルする必要があります。

これらのシンボルの値が、Visual Studio ソリューションのプロジェクト全体で一貫していることと、使用中のアプリがリンクしているコードとライブラリに一致していることを確認してください。

## <a name="third-party-library-issues-and-vcpkg"></a>サードパーティライブラリの問題と vcpkg

ビルドの一部としてサードパーティのライブラリを構成しようとしているときにこのエラーが表示される場合は、C++ パッケージマネージャーである [vcpkg](../../build/vcpkg.md)を使用してライブラリをインストールし、ビルドすることを検討してください。 vcpkg は、多数 [のサードパーティ製ライブラリ](https://github.com/Microsoft/vcpkg/tree/master/ports)をサポートしており、プロジェクトの一部として成功したビルドに必要なすべての構成プロパティと依存関係を設定します。

## <a name="see-also"></a>関連項目

[リンカーツールのエラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
