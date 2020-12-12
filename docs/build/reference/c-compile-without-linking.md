---
description: 詳細情報:/c (リンクなしでコンパイル)
title: /c (リンクを行わないコンパイル)
ms.date: 11/04/2016
f1_keywords:
- /c
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
ms.openlocfilehash: b9dd692dd99cddf63015fe26e37dc54841816f7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179370"
---
# <a name="c-compile-without-linking"></a>/c (リンクを行わないコンパイル)

リンクの自動呼び出しを禁止します。

## <a name="syntax"></a>構文

```
/c
```

## <a name="remarks"></a>解説

**/C** を使用してコンパイルすると、.obj ファイルのみが作成されます。 ビルドのリンクフェーズを実行するには、適切なファイルとオプションを使用して明示的にリンクを呼び出す必要があります。

開発環境で作成された内部プロジェクトは、既定で **/c** オプションを使用します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

- このオプションは、開発環境内では使用できません。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムによって設定するには、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>」を参照してください。

## <a name="example"></a>例

次のコマンドラインでは、オブジェクトファイルを最初の .obj と2番目の .obj に作成します。3番目の .obj は無視されます。

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

実行可能ファイルを作成するには、リンクを呼び出す必要があります。

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
