---
description: /Zp (構造体メンバーの配置) の詳細情報
title: /Zp (構造体メンバーの配置)
ms.date: 01/08/2021
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
ms.openlocfilehash: 8d29c442726aff9503a42378fce6a7b8b09526ed
ms.sourcegitcommit: 14d6ae0d527d05d153e26463d4cd5ada0f43e864
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "98104779"
---
# <a name="zp-struct-member-alignment"></a>/Zp (構造体メンバーの配置)

構造体のメンバーをメモリにパックする方法を制御し、モジュール内のすべての構造体を同様にパッキングするよう指定します。

## <a name="syntax"></a>構文

> **`/Zp`**[**`1`**|**`2`**|**`4`**|**`8`**|**`16`**]

## <a name="remarks"></a>解説

**`/ZpN`** オプションは、各構造体メンバーを格納する場所をコンパイラに指定します。 コンパイラは、メンバーの型のサイズまたは *N* バイト境界のいずれか小さい方の境界上にある最初のメンバーの後にメンバーを格納します。

次の表に、使用可能なパック値を示します。

|/Zp 引数|結果|
|-|-|
|1|構造体を 1 バイト境界にパックします。 **`/Zp`** と同じ。|
|2|構造体を 2 バイト境界にパックします。|
|4|構造体を 4 バイト境界にパックします。|
|8|構造体を 8 バイト境界にパックします (x86、ARM、および ARM64 の既定値)。|
|16| 構造体を 16 バイト境界にパックします (x64 の既定値)。|

配置に特定の要件がない場合は、このオプションを使用しないでください。

> [!WARNING]
> Windows SDK の C/C++ ヘッダーは、内部で **`/Zp8`** でパックされることを想定しています。 Windows SDK ヘッダーを含める際には、コマンドラインで **`/Zp`** を使用したり、`#pragma pack` を使用したりして既定の設定を変更しないでください。 変更した場合、アプリケーションの実行時にメモリ破損などの問題が生じるおそれがあります。

構造体のパックの制御には、[`pack` プラグマ](../../preprocessor/pack.md)を使用することも可能です。 アラインメントの詳細については、次のトピックを参照してください。

- [`align`](../../cpp/align-cpp.md)

- [`alignof` 演算子](../../cpp/alignof-operator.md)

- [`__unaligned`](../../cpp/unaligned.md)

- [`/ALIGN` (セクション配置)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[コード生成]** プロパティ ページを選択します。

1. **[構造体メンバーのアラインメント]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md) \
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
