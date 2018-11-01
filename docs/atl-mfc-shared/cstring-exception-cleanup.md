---
title: '文字列: CString の例外の後処理'
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: f1950553e3bf3a43f029478e00b177f5cbfe121f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492548"
---
# <a name="cstring-exception-cleanup"></a>文字列: CString の例外の後処理

MFC の以前のバージョンでクリーンアップすることが重要でした[CString](../atl-mfc-shared/reference/cstringt-class.md)使用後にオブジェクト。 MFC バージョン 3.0 以降では、明示的なクリーンアップは必要ではありません。

C++ 例外処理機構 MFC を今すぐ使用する、例外の後にクリーンアップについて心配する必要はありません。 方法の説明について C++""がスタックをアンワインド例外が発生した後は、「 [try catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)します。 MFC を使用する場合でも**お試しください**/**キャッチ**マクロは C++ のキーワードではなく**お試しください**と**キャッチ**MFC、C++ を使用して下には、例外処理機構それでもようにする必要はありませんを明示的にクリーンアップします。

## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[例外処理](../mfc/exception-handling-in-mfc.md)

