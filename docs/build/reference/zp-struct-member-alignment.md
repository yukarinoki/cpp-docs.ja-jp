---
title: -Zp (構造体メンバーの配置) |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1666da40f748d18c762eae19595692addcdbf78a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380863"
---
# <a name="zp-struct-member-alignment"></a>/Zp (構造体メンバーの配置)

メモリに構造体のメンバーをパックする方法を制御し、モジュール内のすべての構造の同じパッキングを指定します。

## <a name="syntax"></a>構文

> **/Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>コメント

指定すると、 **/Zp**_n_オプション、最初は、メンバー型のサイズのどちらかに格納された後は、各構造体メンバーまたは*n*-バイト境界 (ここで*n*が 1、2、4、8、または 16)、小さい方です。

使用可能なパッキング値は次の表に説明します。

|/Zp 引数|効果|
|-|-|
|1|構造体は、1 バイト境界でパックします。 同じ **/Zp**です。|
|2|構造体は、2 バイト境界でパックします。|
|4|構造体は、4 バイト境界でパックします。|
|8|構造体は、(既定値) の 8 バイト境界でパックします。|
|16| 構造体を 16 バイト境界でパックします。|

特定のアラインメント要件がない限りは、このオプションを使用する必要があります。

> [!WARNING]  
> Windows SDK での C++ ヘッダーがあると **/zp8 です**梱包です。 メモリの破損が生じる場合、 **/Zp** Windows SDK のヘッダーを使用する場合、設定を変更します。

使用することも[パック](../../preprocessor/pack.md)制御構造体のパッキングにします。 アラインメントの詳細については、次のトピックを参照してください。

- [align](../../cpp/align-cpp.md)

- [__alignof 演算子](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [構造体の配置例](../../build/examples-of-structure-alignment.md)(x64 固有)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、 **C/C++** > **コード生成**プロパティ ページ。

1. 変更、**構造体メンバーの配置**プロパティです。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>」を参照してください。

## <a name="see-also"></a>関連項目

- [コンパイラ オプション](../../build/reference/compiler-options.md)   
- [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
