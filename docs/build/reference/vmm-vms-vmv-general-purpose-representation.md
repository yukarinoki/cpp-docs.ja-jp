---
description: 詳細については、次を参照してください:/vmm、/dns、/vmv (General Purpose 表現)
title: /vmm、-vm、-vmv (General Purpose 表現)
ms.date: 11/04/2016
f1_keywords:
- /vms
- /vmm
- /vmv
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
ms.openlocfilehash: 8c5761a2f51ec9860a4afeb7d4aacbf7f882b3f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257226"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm、/vms、/vmv (通常の最適化)

[/Vmb、/vmg (表現メソッド)](vmb-vmg-representation-method.md)が[表現メソッド](vmb-vmg-representation-method.md)として選択されている場合に使用されます。 これらのオプションは、まだ検出されていないクラス定義の継承モデルを示します。

## <a name="syntax"></a>構文

```
/vmm
/vms
/vmv
```

## <a name="remarks"></a>解説

これらのオプションの説明を次の表に示します。

|オプション|説明|
|------------|-----------------|
|**/vmm**|クラスのメンバーへのポインターの最も一般的な表現を、多重継承を使用するクラスとして指定します。<br /><br /> [#Pragma pointers_to_members](../../preprocessor/pointers-to-members.md)に対応する [継承キーワード](../../cpp/inheritance-keywords.md)と引数が **multiple_inheritance**。<br /><br /> この表現は、単一継承に必要な値よりも大きくなっています。<br /><br /> メンバーへのポインターが宣言されているクラス定義の継承モデルが virtual の場合、コンパイラはエラーを生成します。|
|**/vms**|クラスのメンバーへのポインターの最も一般的な表現を、継承なしまたは単一継承のいずれかを使用するクラスに指定します。<br /><br /> [#Pragma pointers_to_members](../../preprocessor/pointers-to-members.md)に対応する [継承キーワード](../../cpp/inheritance-keywords.md)と引数が **single_inheritance**。<br /><br /> これは、クラスのメンバーへのポインターの最小の表現です。<br /><br /> メンバーへのポインターが宣言されているクラス定義の継承モデルが multiple または virtual の場合、コンパイラはエラーを生成します。|
|**/vmv**|クラスのメンバーへのポインターの最も一般的な表現を、仮想継承を使用するクラスとして指定します。 これによってエラーが発生することはなく、既定値です。<br /><br /> [#Pragma pointers_to_members](../../preprocessor/pointers-to-members.md)に対応する [継承キーワード](../../cpp/inheritance-keywords.md)と引数が **virtual_inheritance**。<br /><br /> このオプションでは、他のオプションよりも大きなポインターと、ポインターを解釈するためのコードを追加する必要があります。|

これらの継承モデルのオプションのいずれかを指定すると、そのモデルは、継承の種類に関係なく、クラスメンバーへのすべてのポインターに対して使用されます。また、クラスの前または後にポインターが宣言されているかどうかによっても使用されます。 したがって、常に単一継承クラスを使用する場合は、 **/vm** を使用してコンパイルすることで、コードサイズを減らすことができます。ただし、最も一般的なケースを使用する場合は (最大のデータ表現を使用する場合)、 **/vmv** を使用してコンパイルします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/vmb、/vmg (表現メソッド)](vmb-vmg-representation-method.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
