---
title: 共有 (読み取り専用) または計算型シンボル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.shared.calculated
dev_langs:
- C++
helpviewer_keywords:
- symbols, read-only
- symbols, shared
- symbols, calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c56e8af65d27bda8ef04655f40bdd2e335067d3c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879228"
---
# <a name="including-shared-read-only-or-calculated-symbols"></a>共有シンボル (読み取り専用) または計算型シンボルのインクルード
別のアプリケーションによって作成されたリソース ファイルを開発環境に初めて読み取るとき、インクルードされるすべてのヘッダー ファイルが読み取り専用とマークされます。 その後、使用することができます、 [] ダイアログ ボックスの [リソース インクルード](../windows/resource-includes-dialog-box.md)追加の読み取り専用シンボル ヘッダー ファイルを追加します。  
  
 読み取り専用のシンボル定義を使用する状況の 1 つに、複数のプロジェクト間でシンボル ファイルを共有する場合があります。  
  
 インクルードされるシンボル ファイルは、単純な整数の代わりに式を使用してシンボル値を定義するシンボル定義を含む既存のリソースがあるときに使用することもできます。 例えば:  
  
```  
#define   IDC_CONTROL1 2100  
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```  
  
 計算型シンボルは、次の条件が満たされる場合に環境によって適切に解釈されます。  
  
-   計算型シンボルが読み取り専用シンボル ファイルに配置されている。  
  
-   これらの計算型シンボルが既に割り当てられているリソースがリソース ファイルに含まれている。  
  
-   数値式が求められる。  
  
> [!NOTE]
>  文字列または数値式が求められる場合、式は評価されません。  
  
### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>共有 (読み取り専用) シンボルをリソース ファイルに含めるには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)を .rc ファイルを右クリックして[リソースが含まれています](../windows/resource-includes-dialog-box.md)ショートカット メニューからです。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **読み取り専用ヘッダー ファイル**ボックスで使用して、 **#include**コンパイラ ディレクティブを読み取り専用シンボルを格納するファイルを指定します。  
  
     Resource.h を呼び出さないでください。これは、通常、メイン シンボル ヘッダー ファイルで使用されるファイル名です。  
  
    > [!NOTE]
    >  **重要な**入力したとおりにリソース ファイルに含まれるが、読み取り専用ヘッダー ファイル ボックスに入力します。 入力ミスや構文エラーがないことを確認してください。  
  
     使用して、**読み取り専用ヘッダー ファイル**シンボル定義のみを含むファイルをインクルードするボックスです。 リソース定義をインクルードする目的には使用しないでください。そうでないと、ファイルを保存したときに重複するリソース定義が作成されます。  
  
3.  指定したファイルにシンボルを配置します。  
  
     この方法でインクルードされるファイル内のシンボルは、リソース ファイルを開くたびに評価されますが、ファイルを保存するときにディスク上で置き換えられません。  
  
4.  **[OK]** をクリックします。  
  

  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [シンボル名の制限](../windows/symbol-name-restrictions.md)   
 [シンボル値の制限](../windows/symbol-value-restrictions.md)   
 [定義済みシンボル Id](../windows/predefined-symbol-ids.md)   
 [シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)