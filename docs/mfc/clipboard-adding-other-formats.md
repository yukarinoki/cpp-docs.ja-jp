---
title: 'クリップボード: その他の形式の追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67004ac43193d47720626da241a8030ba396abdf
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932020"
---
# <a name="clipboard-adding-other-formats"></a>クリップボード : その他のデータ形式の追加
このトピックでは、特に OLE サポートの場合、サポートされている形式の一覧を展開する方法について説明します。 トピック[クリップボード: データのコピーと貼り付け](../mfc/clipboard-copying-and-pasting-data.md)コピーと、クリップボードから貼り付けをサポートするために必要な最低限の実装について説明します。 クリップボードにコピーのみの形式は、すべてを実装する場合は、 **CF_METAFILEPICT**、 **CF_EMBEDSOURCE**、 **CF_OBJECTDESCRIPTOR**、および可能性のある**CF_LINKSOURCE**です。 ほとんどのアプリケーションでは、これら 3 つよりも、クリップボードにその他の形式を必要があります。  
  
##  <a name="_core_registering_custom_formats"></a> 登録するカスタム書式設定します。  
 独自のカスタム形式を作成するには、独自のクリップボード形式を登録するときに使用する同じ手順を実行: する形式の名前を渡す、**独自のデータ**関数および形式 ID としてその戻り値を使用します。  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> 形式をクリップボードにコピーします。  
 オーバーライドする必要がありますにクリップボードに格納されたものをその他の形式を追加する、`OnGetClipboardData`いずれかから派生するクラスの関数と`COleClientItem`または`COleServerItem`(コピーするデータがネイティブかどうか) に応じて。 この関数では、次の手順を使用する必要があります。  
  
#### <a name="to-place-formats-on-the-clipboard"></a>クリップボードの形式を配置するには  
  
1.  `COleDataSource` オブジェクトを作成します。  
  
2.  このデータ ソースを呼び出すことによってサポートされている形式の一覧に、ネイティブ データ形式を追加する関数に渡す`COleDataSource::CacheGlobalData`です。  
  
3.  標準の形式を呼び出すことによって追加`COleDataSource::CacheGlobalData`をサポートする標準的な形式はごとです。  
  
 この方法は MFC OLE サンプル プログラムで使用される[HIERSVR](../visual-cpp-samples.md) (確認、`OnGetClipboardData`のメンバー関数、**よう**クラス)。 このサンプルでは唯一の違いは、HIERSVR にないその他の標準の形式がサポートされているために、手順 3 が実装されていません。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [OLE データ オブジェクトとデータ ソースと統一されたデータの転送します。](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE のドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>関連項目  
 [クリップボード: OLE クリップボード機構の使用方法](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

