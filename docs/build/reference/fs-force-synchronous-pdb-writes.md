---
description: 詳細については、/FS (同期 PDB 書き込みの強制) に関するページを参照してください。
title: /FS (同期 PDB 書き込みの強制)
ms.date: 11/04/2016
f1_keywords:
- /FS
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
ms.openlocfilehash: 2dcddd046cc7232f40be5a54d73e659ed099e85d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192032"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (同期 PDB 書き込みの強制)

[/Zi](z7-zi-zi-debug-information-format.md)または[/zi](z7-zi-zi-debug-information-format.md)によって作成されたプログラムデータベース (PDB) ファイルへの書き込みを、MSPDBSRV.EXE によってシリアル化するように強制します。

## <a name="syntax"></a>構文

```
/FS
```

## <a name="remarks"></a>解説

既定では、 **/zi** または **/zi** を指定すると、コンパイラは PDB ファイルをロックして、型情報とシンボリックデバッグ情報を書き込みます。 これにより、型の数が多い場合、コンパイル時に型情報の生成にかかる時間が大幅に短くなることがあります。 ウイルス対策プログラムなどの別のプロセスによって PDB ファイルが一時的にロックされている場合、コンパイラによる書き込みは失敗し、重大なエラーが発生することがあります。 この問題は、cl.exe の複数のコピーが同じ PDB ファイルにアクセスするときにも発生することがあります。たとえば、ソリューションで個別のプロジェクトが同じ中間ディレクトリまたは出力ディレクトリを使用する場合や、並列ビルドが有効になっている場合です。 **/Fs** コンパイラオプションを使用すると、コンパイラが PDB ファイルをロックして、MSPDBSRV.EXE 経由で書き込みを強制的に実行できます。これにより、アクセスがシリアル化されます。 これにより、ビルド時間が大幅に長くなることがあります。cl.exe の複数のインスタンスが PDB ファイルに同時にアクセスするときに発生する可能性があるすべてのエラーを防止できないこともあります。 個別のプロジェクトによりそれぞれ別々の中間ディレクトリと出力ディレクトリに書き込まれるように、または、他のプロジェクトに依存するいずれかのプロジェクトでプロジェクトのビルドがシリアル化されるように、ソリューションを変更することをお勧めします。

[/Mp](mp-build-with-multiple-processes.md)オプションを使用すると、既定で **/fs** が有効になります。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **C/c + +** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. を含めるように " **追加オプション** " プロパティを変更し、[ `/FS` **OK]** を選択します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
