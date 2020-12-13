---
description: 詳細情報:/Zf (PDB 生成の高速化)
title: /Zf (PDB 生成の高速化)
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: 6acf84de3c286131f470808505cdf0e895feeaeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178889"
---
# <a name="zf-faster-pdb-generation"></a>/Zf (PDB 生成の高速化)

mspdbsrv.exe の RPC 呼び出しを最小限にすることで、並列ビルドでの PDB の生成速度を向上させることができます。

## <a name="syntax"></a>構文

> **/Zf**

## <a name="remarks"></a>解説

**/Zf** オプションを使用すると、 [/mp (複数のプロセスを使用したビルド)](mp-build-with-multiple-processes.md)オプションを使用する場合、またはビルドシステム ( [MSBuild](/visualstudio/msbuild/msbuild-reference)や [cmake](../cmake-projects-in-visual-studio.md)など) が複数の cl.exe コンパイラプロセスを同時に実行する場合に、コンパイラサポートによって PDB ファイルをより迅速に生成できます。 このオプションを指定すると、コンパイラのフロントエンドは、コンパイルが終了するまで PDB ファイル内の型のレコードごとに型インデックスの生成を遅延させ、各レコードに対して RPC 要求を行うのではなく、1回の RPC 呼び出しでそれらすべてを mspdbsrv.exe に要求します。 これにより、複数の cl.exe コンパイラプロセスが同時に実行される環境で mspdbsrv.exe プロセスの RPC 負荷を軽減することで、ビルドのスループットを大幅に向上させることができます。

**/Zf** オプションは PDB の生成にのみ適用されるため、 [/Zi](z7-zi-zi-debug-information-format.md)または [/zi](z7-zi-zi-debug-information-format.md)オプションが必要です。

**/Zf** オプションは、Visual Studio 2017 バージョン15.1 以降で使用できます。既定ではオフになっています。 Visual Studio 2017 バージョン 15.7 Preview 3 以降では、 **/zi** または **/zi** オプションが有効になっている場合、このオプションは既定でオンになっています。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション** ] プロパティを変更して **/Zf** を含め、[ **OK]** を選択します。

## <a name="see-also"></a>関連項目

[アルファベット順のコンパイラ オプション](compiler-options-listed-alphabetically.md)<br/>
[/MP (複数のプロセスを使用したビルド)](mp-build-with-multiple-processes.md)<br/>
