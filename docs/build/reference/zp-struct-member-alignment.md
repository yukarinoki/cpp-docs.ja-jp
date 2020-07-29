---
title: /Zp (構造体メンバーの配置)
ms.date: 04/04/2019
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: c78e670303bde68299725e18c6f588f5e410a971
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234303"
---
# <a name="zp-struct-member-alignment"></a>/Zp (構造体メンバーの配置)

構造体のメンバーをメモリにパックする方法を制御し、モジュール内のすべての構造体に対して同じパッキングを指定します。

## <a name="syntax"></a>構文

> **`/Zp`**[**`1`**|**`2`**|**`4`**|**`8`**|**`16`**]

## <a name="remarks"></a>解説

オプションは、 **`/ZpN`** 各構造体メンバーを格納する場所をコンパイラに指示します。 コンパイラは、メンバー型のサイズまたは*N*バイトの境界のいずれか小さい方の境界上にある最初のメンバーの後にメンバーを格納します。

次の表で、使用可能なパッキング値について説明します。

|/Zp 引数|効果|
|-|-|
|1|構造体を1バイト境界でパックします。 と同じ **`/Zp`** です。|
|2|構造体を2バイト境界でパックします。|
|4|構造体を4バイト境界でパックします。|
|8|構造体を8バイト境界でパックします (x86、ARM、および ARM64 の既定値)。|
|16| 構造体を16バイト境界でパックします (x64 の既定値)。|

特定のアラインメント要件がない場合は、このオプションを使用しないでください。

> [!WARNING]
> Windows SDK セットの C++ ヘッダーは、内部的にパッキングを想定し **`/Zp8`** ます。 **`/Zp`** Windows SDK ヘッダー内で設定が変更された場合、メモリの破損が発生する可能性があります。 ヘッダーは、 **`/Zp`** コマンドラインで設定したオプションの影響を受けません。

また、を使用して、 [`pack`](../../preprocessor/pack.md) 構造のパッキングを制御することもできます。 アラインメントの詳細については、次のトピックを参照してください。

- [`align`](../../cpp/align-cpp.md)

- [`alignof` 演算子](../../cpp/alignof-operator.md)

- [`__unaligned`](../../cpp/unaligned.md)

- [`/ALIGN`(セクションの配置)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コード生成**] プロパティページを選択します。

1. **構造体メンバーのアラインメント**プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md) \
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
