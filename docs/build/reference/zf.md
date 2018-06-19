---
title: /Zf (高速 PDB の生成) |Microsoft ドキュメント
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zf
dev_langs:
- C++
helpviewer_keywords:
- /Zf
- -Zf
author: corob-msft
ms.author: corob
ms.openlocfilehash: 968ce17302fa608888c7ae2fedf695946b0119bd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379966"
---
# <a name="zf-faster-pdb-generation"></a>/Zf (高速 PDB 生成を)

Mspdbsrv.exe への RPC 呼び出しを最小化して並行ビルドでは高速の PDB 生成を有効にします。

## <a name="syntax"></a>構文

> **/Zf**

## <a name="remarks"></a>コメント

**/Zf**オプションを使用するときに PDB ファイルの生成を高速のコンパイラ サポートを有効、 [/MP (複数のプロセスでビルド)](mp-build-with-multiple-processes.md)オプション、またはビルド システム (たとえば、 [MSBuild](/visualstudio/msbuild/msbuild-reference)または[CMake](../../ide/cmake-tools-for-visual-cpp.md)) が複数の cl.exe コンパイラで同時に実行します。 このオプションは、コンパイラのフロント エンド、コンパイルが終了するまでの PDB ファイル内の各種類レコードの型のインデックスの生成を遅延すると、し、各レコードの RPC 要求を行うのではなく、mspdbsrv.exe に 1 回の RPC 呼び出しのすべてが要求します。 複数の cl.exe コンパイラ プロセスが同時に実行する環境で mspdbsrv.exe プロセスの RPC の負荷を減らすことによってビルド スループットを向上このことが大幅にします。

**/Zf**オプションは、PDB の生成にのみ適用されます、必要な[/Zi](z7-zi-zi-debug-information-format.md)または[/ZI](z7-zi-zi-debug-information-format.md)オプション。

**/Zf**オプションでは、以降では、Visual Studio 2017 バージョン 15.1、使用できる場所が既定ではオフです。 以降では、Visual Studio 2017 バージョン 15.7 Preview 3 では、このオプションは既定でオンときに、 **/Zi**または **/ZI**オプションが有効にします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zf**を選択し**OK**です。

## <a name="see-also"></a>関連項目

[アルファベット順のコンパイラ オプション](compiler-options-listed-alphabetically.md)<br/>
[/MP (複数のプロセスを使用したビルド)](mp-build-with-multiple-processes.md)<br/>
