---
title: vmm、vm--vmv (汎用表現) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vms
- /vmm
- /vmv
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd2f79238c890d43678332203acbe9d935a54102
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm、/vms、/vmv (通常の最適化)
際に使用される[/vmb、/vmg () を処理形式](../../build/reference/vmb-vmg-representation-method.md)として選択されて、[表現メソッド](../../build/reference/vmb-vmg-representation-method.md)です。 これらのオプションでは、not まだ検出クラス定義の継承モデルを示しています。  
  
## <a name="syntax"></a>構文  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## <a name="remarks"></a>コメント  
 これらのオプションの説明を次の表に示します。  
  
|オプション|説明|  
|------------|-----------------|  
|**/vmm**|多重継承を使用するいずれかを指定するには、クラスのメンバーへのポインターの最も一般的な表現を指定します。<br /><br /> 対応する[継承キーワード](../../cpp/inheritance-keywords.md)とする引数[#pragma pointers_to_members](../../preprocessor/pointers-to-members.md)は**multiple_inheritance**です。<br /><br /> この表現は、単一継承で必要となるより大きいです。<br /><br /> メンバーへのポインターが宣言されているクラス定義の継承モデルが仮想の場合、コンパイラはエラーを生成します。|  
|**/vms**|ありません継承または単一継承のいずれかを使用するいずれかを指定するには、クラスのメンバーへのポインターの最も一般的な表現を指定します。<br /><br /> 対応する[継承キーワード](../../cpp/inheritance-keywords.md)とする引数[#pragma pointers_to_members](../../preprocessor/pointers-to-members.md)は**single_inheritance**です。<br /><br /> これは、クラスのメンバーへのポインターの最小サイズの表現です。<br /><br /> メンバーへのポインターが宣言されているクラス定義の継承モデルが複数ある場合または仮想、コンパイラ エラーが発生します。|  
|**/vmv**|仮想継承を使用するいずれかを指定するには、クラスのメンバーへのポインターの最も一般的な表現を指定します。 ありません、エラーが発生し、既定値です。<br /><br /> 対応する[継承キーワード](../../cpp/inheritance-keywords.md)とする引数[#pragma pointers_to_members](../../preprocessor/pointers-to-members.md)は**virtual_inheritance**です。<br /><br /> このオプションは、大きいサイズのポインターと他のオプションよりもポインターを解釈する追加のコードが必要です。|  
  
 これらの継承モデル オプションのいずれかを指定すると、そのモデルが、クラス後の継承の種類や前に、またはにポインターを宣言するかどうかに関係なく、クラス メンバーへのすべてのポインターに対して使用されます。 そのため、常に単一継承のクラスを使用する場合は、コードのサイズを小さくでコンパイルする **/vms**ただし、最も一般的なケース (を犠牲にして、最大のデータ表現) を使用する場合は、コンパイル時に**。/vmv**です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [/vmb、/vmg)](../../build/reference/vmb-vmg-representation-method.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)