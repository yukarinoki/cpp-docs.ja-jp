---
title: /GF (同一文字列の削除)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: c85379cf1a514cafcd2f840673fc9c7b2d415ba4
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425667"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (同一文字列の削除)

実行中に、プログラム イメージではメモリ内に同一文字列の 1 つのコピーを作成するコンパイラを有効にします。 これは、最適化と呼ばれる*文字列プール*小さいプログラムを作成することができます。

## <a name="syntax"></a>構文

```
/GF
```

## <a name="remarks"></a>Remarks

使用する場合 **/GF**、オペレーティング システムのメモリの文字列の部分が交換されていないと、文字列は、イメージ ファイルからバックアップを読み取ることができます。

**/GF**読み取り専用として文字列をプールします。 文字列を変更しようとする場合 **/GF**、アプリケーション エラーが発生します。

文字列プールにより、何が 1 つのバッファーに複数のポインターにする複数のバッファーに複数のポインターとして対象としています。 次のコードで`s`と`t`同じ文字列で初期化されます。 文字列プールことによってそれらの同じメモリを指すようにします。

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 、エディット コンティニュを使用するオプションが自動的に設定、 **/GF**オプション。

> [!NOTE]
>  **/GF**コンパイラ オプションはそれぞれ一意の文字列のアドレス指定可能なセクションを作成します。 既定では、オブジェクト ファイルには最大で 65,536 個のアドレス指定可能なセクションも含めることができます。 使用して、プログラムが 65,536 を超える文字列が含まれる場合、 [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)コンパイラ オプションを複数のセクションを作成します。

**/GF**ときは、 [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)または **/O2**使用されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**コード生成**プロパティ ページ。

1. 変更、**文字列プールを有効にする**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
