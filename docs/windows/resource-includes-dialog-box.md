---
title: '[リソース インクルード] ダイアログ ボックス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourceincludes
dev_langs:
- C++
helpviewer_keywords:
- Resource Includes dialog box
- rc files, changing storage
- symbol header files, changing
- compiling source code, including resources
- .rc files, changing storage
- symbol header files, read-only
- symbols, symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 756289bb819809fed63dba579c4ad1cd1e975780
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879673"
---
# <a name="resource-includes-dialog-box"></a>[リソース インクルード] ダイアログ ボックス
使用することができます、**リソースが含まれています**を通常の動作形態プロジェクトの .rc ファイル内のすべてのリソースを格納する環境の変更 ダイアログ ボックス[シンボル](../windows/symbols-resource-identifiers.md)Resource.h にします。  
  
 開くには、**リソースが含まれています**ダイアログ ボックスで、右クリックして .rc ファイルを[リソース ビュー](../windows/resource-view-window.md)、順に選択**リソースが含まれています**ショートカット メニューからです。  
  
 **シンボル ヘッダー ファイル**  
 リソース ファイルのシンボル定義が格納されているヘッダー ファイルの名前を変更することができます。 詳細については、次を参照してください。[シンボル ヘッダー ファイルの名前を変更する](../windows/changing-the-names-of-symbol-header-files.md)です。  
  
 **読み取り専用ヘッダー ファイル**  
 編集セッション中に変更してはいけないシンボルが格納されているヘッダー ファイルをインクルードすることができます。 たとえば、いくつかのプロジェクト間で共有されるシンボル ファイルをインクルードできます。 MFC の .h ファイルをインクルードすることもできます。 詳細については、次を参照してください。[共有 (読み取り専用) または計算型シンボル](../windows/including-shared-read-only-or-calculated-symbols.md)です。  
  
 **コンパイル時ディレクティブ**  
 メイン リソース ファイルのリソースとは個別に作成および編集されたリソース ファイルをインクルードしたり、コンパイル時ディレクティブ (たとえば、条件付きでリソースをインクルードするディレクティブなど) を含めたり、カスタム形式のリソースを含めたりすることができます。 また、[コンパイル時に追加するファイル] ボックスを使用して、標準 MFC リソース ファイルをインクルードすることもできます。 詳細については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)です。  
  
> [!NOTE]
>  マークされた .rc ファイルにこれらのテキスト ボックス内のエントリが表示される`TEXTINCLUDE 1`、 `TEXTINCLUDE 2`、および`TEXTINCLUDE 3`それぞれします。 詳細については、次を参照してください。 [TN035: 複数のリソース ファイルを使用すると、Visual c ヘッダー ファイル](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)です。  
  
 使用してリソース ファイルを変更した後、**リソースが含まれています**ダイアログ ボックスで、.rc ファイルを閉じてから開き、変更を有効にするために必要があります。 詳細については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)です。  
  

  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [方法: 指定リソースのインクルード ディレクトリ](../windows/how-to-specify-include-directories-for-resources.md)   
 [シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)