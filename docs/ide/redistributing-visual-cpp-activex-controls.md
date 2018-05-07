---
title: Visual C ActiveX コントロールを再配布 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b770bbacca06c6edfb3b9b4eda53fc7be8a7ae0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-visual-c-activex-controls"></a>Visual C++ ActiveX コントロールの再配布
Visual C 6.0 では、再配布するアプリケーションで使用できる ActiveX コントロールが用意されています。 Visual C では、これらのコントロールは含まれていません。 Visual C 6.0 のライセンス契約、あたり Visual C で開発されたアプリケーションでこれらのコントロールを再配布することができます。  
  
> [!NOTE]
>  Visual C 6.0 は Microsoft によってサポートされていません。  
  
 再頒布可能パッケージの Visual C 6.0 の ActiveX コントロールの一覧は、ディスクの 1 つの Visual C 6.0 製品 CD に Common\Redist\Redist.txt を参照してください。  
  
 アプリケーションを配布するときにインストールし、(Regsvr32.exe を使用)、ActiveX コントロールの .ocx ファイルを登録する必要があります。 さらに、対象のコンピュータが、次のシステム ファイル (アスタリスクは、ファイルを登録する必要があることを示します) の現在のバージョンを確認する必要があります。  
  
-   asycfilt.dll  
  
-   Comcat.dll *  
  
-   Oleaut32.dll *  
  
-   Olepro32.dll *  
  
-   stdole2.tlb  
  
 これらの Dll が、ターゲット システムで利用できない場合は、対応するオペレーティング システムを更新するため、所定のメカニズムを使用して更新を取得する必要があります。 Windows オペレーティング システムからの最新の service pack をダウンロードする[ http://windowsupdate.microsoft.com](http://windowsupdate.microsoft.com)です。  
  
 アプリケーションでは、データベースに接続する ActiveX コントロールのいずれかを使用する場合は、Microsoft Data Access Components (MDAC) が、ターゲット システムにインストールされているが必要です。 詳細については、次を参照してください。[データベース サポート ファイルの再配布](../ide/redistributing-database-support-files.md)です。  
  
 データベースに接続する ActiveX コントロールを使用する場合は、ターゲット コンピューターのデータ ソース名をレプリケートする必要があります。 これを行うプログラムで関数をなど`ConfigDSN`です。  
  
 再頒布可能パッケージの一部の ActiveX コントロールでは、追加の依存関係があります。 上の各 .ocx ファイル Os\System フォルダーに、Visual C 6.0 製品 CD、.dep ファイルもあります。 再配布する .ocx ファイルごとに対応する .dep ファイル内の 1 つまたは複数の用途エントリを探します。 ファイルが表示されている場合は、ファイルが、ターゲット コンピューター上であることを確認する必要があります。 すべての Dll を登録する必要がある .ocx ファイルを直接サポートします。 (を成功させるのには、Regsvr32.exe を対象となるコンピューター含める必要がありますまずすべてのコントロールを静的に読み込む Dll です。)さらに、依存関係として記載されている DLL もある場合、.dep ファイル、Os\System CD のフォルダーに、Visual C 6.0、.dep のファイルを使用してエントリも調査する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)