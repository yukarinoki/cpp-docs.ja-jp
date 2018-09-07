---
title: CString の例外の後処理 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 656739ad000612f130f5cdfb1a53a6de2d67c4c8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761369"
---
# <a name="cstring-exception-cleanup"></a>文字列: CString の例外の後処理

MFC の以前のバージョンでクリーンアップすることが重要でした[CString](../atl-mfc-shared/reference/cstringt-class.md)使用後にオブジェクト。 MFC バージョン 3.0 以降では、明示的なクリーンアップは必要ではありません。

C++ 例外処理機構 MFC を今すぐ使用する、例外の後にクリーンアップについて心配する必要はありません。 方法の説明について C++""がスタックをアンワインド例外が発生した後は、「 [try catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)します。 MFC を使用する場合でも**お試しください**/**キャッチ**マクロは C++ のキーワードではなく**お試しください**と**キャッチ**MFC、C++ を使用して下には、例外処理機構それでもようにする必要はありませんを明示的にクリーンアップします。

## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
[例外処理](../mfc/exception-handling-in-mfc.md)

