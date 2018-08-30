---
title: 'クリップボード: OLE クリップボード機構の使用 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d37618dccabd576a67c8b82a8b8ab38246254070
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214706"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>クリップボード : OLE クリップボード機構の使用方法
OLE は、クリップボードを使用してデータを転送するための標準形式といくつかの特定の OLE 形式を使用します。  
  
 切り取りまたはアプリケーションからデータをコピーするときに、データが貼り付け操作で使用されるクリップボードに格納されます。 このデータは、さまざまな形式では。 クリップボードからデータを貼り付けるときに、アプリケーションはこれらの形式を使用するを選択できます。 具体的に特定の形式で貼り付けを使用していない場合は、ほとんどの情報を提供する形式を選択する、アプリケーションを作成する必要があります。 読み取りをする可能性があります、続行する前に、[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)トピック。 これらには、データが、作業を転送する方法と、アプリケーションでそれらを実装する方法の基本について説明します。  
  
 Windows では、さまざまなクリップボードを使用してデータを転送するために使用できる標準の形式を定義します。 これらは、メタファイル、テキスト、ビットマップ、およびその他のユーザーが含まれます。 OLE では、さまざまな OLE に固有の書式を定義します。 これらの標準形式で指定したよりも詳細を必要とするアプリケーションでは、独自のカスタム クリップボード形式を登録することをお勧めを勧めします。 Win32 API 関数を使用して[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)これを行う。  
  
 たとえば、Microsoft Excel スプレッドシート用のカスタム形式を登録します。 この形式はより多くの情報よりも、たとえば、ビットマップします。 このデータをスプレッドシート形式をサポートするアプリケーションに貼り付けると、すべての数式と、スプレッドシートから値が保持される、通常の必要に応じて更新できます。 Microsoft Excel は、OLE アイテムとして貼り付けができるようにもデータとの形式でクリップボードに配置します。 すべての OLE ドキュメント コンテナーには、埋め込みアイテムとしてこの情報を貼り付けることができます。 この埋め込みアイテムは、Microsoft Excel を使用して変更できます。 クリップボードには、単純なスプレッドシートの選択範囲のイメージのビットマップも含まれています。 これはまた、OLE ドキュメント コンテナーやペイントなどのビットマップ エディターに貼り付けることができます。 ビットマップの場合はありません、スプレッドシート データを操作する方法です。  
  
 を、クリップボードから情報の最大量を取得するには、アプリケーションが、クリップボードからデータを貼り付ける前にこれらのカスタム形式の確認する必要があります。  
  
 たとえば、[切り取り] コマンドを有効にする可能性がありますハンドラーを記述する、次のような。  
  
 [!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います  
  
-   [コピーと貼り付けデータ](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [その他のデータ形式の追加](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows クリップボードの使用方法](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [OLE データ オブジェクトとデータ ソースと統一されたデータの転送します。](../mfc/data-objects-and-data-sources-ole.md)  
  
## <a name="see-also"></a>関連項目  
 [クリップボード](../mfc/clipboard.md)

