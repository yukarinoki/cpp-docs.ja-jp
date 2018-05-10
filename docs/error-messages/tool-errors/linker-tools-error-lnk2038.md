---
title: リンカ ツール エラー LNK2038 |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2038
dev_langs:
- C++
helpviewer_keywords:
- LNK2038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f97f65bbe31e51e5083b34949b47a6963696ee37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2038"></a>リンカ ツール エラー LNK2038

> 不一致が検出された '*名前*': 値'*value_1*'値と一致しません'*value_2*' で *<filename.obj>*

シンボルの不一致がリンカーによって検出されました。 このエラーは、アプリへのリンクが競合するシンボル定義を使用して、ライブラリまたはその他のオブジェクトを含む、アプリのさまざまな部分のコードを示します。 [の不一致を検出](../../preprocessor/detect-mismatch.md)プラグマはこのようなシンボルを定義して、競合する値を検出するために使用します。

## <a name="possible-causes-and-solutions"></a>考えられる原因と解決策

このエラーは、プロジェクトのオブジェクト ファイルが古い形式のときに発生する可能性があります。 このエラーに対して他のソリューションを実行する前に、オブジェクト ファイルが最新であることを検証するために、クリーン ビルドを実行してください。

Visual Studio は、実行時エラーまたはその他の予測できない動作を発生させる可能性のある互換性のないコードのリンクを防ぐために、次のシンボルを定義します。

- `_MSC_VER`  
   アプリまたはライブラリのビルドに使用される Visual C++ コンパイラのメジャー バージョン番号とマイナー バージョン番号を示します。 Visual C++ コンパイラの 1 種類のバージョンを使用してコンパイルされたコードは、さまざまなメジャー バージョン番号とマイナー バージョン番号のあるバージョンを使用してコンパイルされたコードと互換性がありません。 詳細については、次を参照してください。`_MSC_VER`で[定義済みマクロ](../../preprocessor/predefined-macros.md)です。

   Visual C コンパイラを使用していると、取得またはライブラリの互換性のあるバージョンをビルドすることはできませんのバージョンと互換性がないライブラリをリンクする場合、プロジェクトをビルドする以前のバージョンのコンパイラを使用することができます変更する、 <。c1/>プラットフォーム ツールセット**以前のツールセットをプロジェクトのプロパティです。 詳細については、次を参照してください。[する方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更](../../build/how-to-modify-the-target-framework-and-platform-toolset.md)です。

- `_ITERATOR_DEBUG_LEVEL`  
   C++ 標準ライブラリで有効になっているセキュリティ機能とデバッグ機能のレベルを示します。 これらの機能は、特定の C++ 標準ライブラリのオブジェクトの表示を変更できるため、こうしたオブジェクトは、異なるセキュリティ機能とデバッグ機能を使用するオブジェクトと互換性がなくなります。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md)」を参照してください。

- `RuntimeLibrary`  
   アプリまたはライブラリで使用する C++ 標準ライブラリおよび C ランタイムのバージョンを示します。 C++ 標準ライブラリまたは C ランタイムの 1 種類のバージョンを使用するコードは、異なるバージョンを使用するコードと互換性がありません。 詳細については、「[/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。

- `_PPLTASKS_WITH_WINRT`  
   使用するコードを示す、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)に対して別の設定を使用してコンパイルされたオブジェクトにリンクされて、 [/ZW](../../build/reference/zw-windows-runtime-compilation.md)コンパイラ オプション。 (**/ZW**サポート C + + CX)。同じを使用して使用したり、PPL に依存するコードをコンパイルする必要があります **/ZW**アプリの残りの部分で使用されている設定です。

これらのシンボルの値が、Visual Studio ソリューションのプロジェクト全体で一貫していることと、使用中のアプリがリンクしているコードとライブラリに一致していることを確認してください。

## <a name="third-party-library-issues-and-vcpkg"></a>サード パーティ製のライブラリの問題と Vcpkg

ビルドの一部として、サード パーティ製ライブラリを構成しようとしているときにこのエラーが発生する場合は、使用を検討して[Vcpkg](../../vcpkg.md)Visual C のパッケージ マネージャーをインストールしてから、ライブラリを作成します。 Vcpkg サポートされている大規模なおよび成長[サード パーティ製のライブラリの一覧](https://github.com/Microsoft/vcpkg/tree/master/ports)、およびすべての構成プロパティと、プロジェクトの一部として、成功したビルドの必要な依存関係を設定します。 詳細については、関連するを参照してください[Visual C ブログ](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/)を投稿します。

## <a name="see-also"></a>関連項目

[リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)