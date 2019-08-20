---
title: '文字列: CString の例外の後処理'
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: d131ce8ebe5158d7f3a567580064068742b63707
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236629"
---
# <a name="cstring-exception-cleanup"></a>文字列: CString の例外の後処理

MFC の以前のバージョンでクリーンアップすることが重要でした[CString](../atl-mfc-shared/reference/cstringt-class.md)使用後にオブジェクト。 MFC バージョン 3.0 以降では、明示的なクリーンアップは必要ではありません。

現在 MFC が使用しているC++ 例外処理メカニズムでは、例外の後にクリーンアップについて心配する必要はありません。 例外の発生後、C++ のスタックを "アンワインド" する方法の説明について は [try、catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md) を参照してください。 C++ のキーワード である **TRY**/**CATCH** ではなく、MFC **try**と**catch** マクロを使用する場合でも、MFC はその下にある C++ 例外メカニズムを使用するため、明示的にクリーンアップする必要はありません。


## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[例外処理](../mfc/exception-handling-in-mfc.md)
