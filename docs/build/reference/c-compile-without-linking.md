---
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
ms.openlocfilehash: 6be3b15efb56e97d658edb5890c3bdce4f64fbd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625148"
---
# <a name="c-compile-without-linking"></a>/c (リンクを行わないコンパイル)

リンクの自動呼び出しができないようにします。

## <a name="syntax"></a>構文

```
/c
```

## <a name="remarks"></a>Remarks

使用してコンパイル **/c** .obj ファイルのみを作成します。 リンクは、適切なファイルとビルドのリンク フェーズを実行するためのオプションを明示的に呼び出す必要があります。

開発環境で作成された内部プロジェクトを使用して、 **/c**既定ではオプションです。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

- このオプションは、開発環境内からご利用いただけません。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムによって設定するには、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>」を参照してください。

## <a name="example"></a>例

次のコマンドラインは、FIRST.obj と SECOND.obj オブジェクト ファイルを作成します。THIRD.obj は無視されます。

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

実行可能ファイルを作成するには、リンクを呼び出す必要があります。

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)