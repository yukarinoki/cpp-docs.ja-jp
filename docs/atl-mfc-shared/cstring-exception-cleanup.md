---
title: '文字列: CString の例外の後処理'
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: 48c8f1c0040236a4f7bf27a2d5ad985ae343c03a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222057"
---
# <a name="cstring-exception-cleanup"></a>文字列: CString の例外の後処理

以前のバージョンの MFC では、使用後に[CString](../atl-mfc-shared/reference/cstringt-class.md)オブジェクトをクリーンアップすることが重要でした。 MFC バージョン3.0 以降では、明示的なクリーンアップは不要になりました。

MFC が現在使用している C++ 例外処理機構の下では、例外発生後のクリーンアップについて心配する必要はありません。 例外がキャッチされた後に C++ がスタックを "アンワインド" する方法の詳細については、「 [try、catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)」を参照してください。 C++ のキーワードではなく mfc の**try**CATCH マクロを使用する場合でも、mfc では c++ の例外機構を使用するので、 / **CATCH** **`try`** **`catch`** 明示的にクリーンアップする必要はありません。


## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[例外処理](../mfc/exception-handling-in-mfc.md)
