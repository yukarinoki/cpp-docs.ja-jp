---
title: 'クリップボード: OLE クリップボード機構の使用 |Microsoft ドキュメント'
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
ms.openlocfilehash: d4940c614046e3ca407887e05e84c811a156d9c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342538"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>クリップボード : OLE クリップボード機構の使用方法
OLE は、クリップボードを使用してデータを転送するための標準形式といくつかの特定の OLE 形式を使用します。  
  
 切り取りまたはアプリケーションからデータをコピーするときに、データが貼り付け操作で使用する、クリップボードに格納されます。 このデータは、さまざまな形式でです。 クリップボードからデータを貼り付けるときに、アプリケーションがどのを使用する形式を選択できます。 具体的に特定の形式を使用して貼り付けしない限り、ほとんどの情報を提供する形式を選択するには、アプリケーションを記述する必要があります。 続行する前にすることも読み取り、[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)トピックです。 これらには、データが、作業を転送する方法と、アプリケーションでそれらを実装する方法の基礎がについて説明します。  
  
 Windows では、クリップボードを使用してデータを転送するために使用できる標準の形式の数を定義します。 メタファイル、テキスト、ビットマップ、およびその他のユーザーが含まれます。 OLE では、さまざまな OLE に固有の書式を定義します。 これらの標準形式で指定されたより詳しいを必要とするアプリケーションでは、独自のカスタム クリップボード形式を登録することをお勧めを勧めします。 Win32 API 関数を使用して[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)これを行う。  
  
 たとえば、Microsoft Excel スプレッドシート用のカスタム書式指定を登録します。 この形式の実行よりも、例の詳細については、ビットマップします。 このデータはスプレッドシート形式をサポートしているアプリケーションへの貼り付け、すべての数式とスプレッドシートの値が保持され、必要な場合に更新することができます。 Microsoft Excel は、OLE アイテムとして貼り付けできるようにもデータとの形式でクリップボードに配置します。 すべての OLE ドキュメント コンテナーは、埋め込みアイテムとしてこの情報を貼り付けることができます。 この埋め込みアイテムは、Microsoft Excel を使用して変更できます。 クリップボードには、スプレッドシートで選択した範囲のイメージの単純なビットマップも含まれています。 これはまた、OLE ドキュメント コンテナーやペイントなどのビットマップ エディターに貼り付けることができます。 場合は、ビットマップ、ただしはありません、スプレッドシート、データを操作する方法です。  
  
 クリップボードから最大限の情報を取得するには、アプリケーションは、クリップボードからデータを貼り付ける前にこれらのカスタム形式にチェックする必要があります。  
  
 たとえば、切り取りコマンドを有効にするには、するは、次のようなハンドラーする記述します。  
  
 [!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [コピーと貼り付けデータ](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [その他の形式の追加](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows クリップボードの使用方法](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [OLE データ オブジェクトとデータ ソースと統一されたデータの転送します。](../mfc/data-objects-and-data-sources-ole.md)  
  
## <a name="see-also"></a>関連項目  
 [クリップボード](../mfc/clipboard.md)

