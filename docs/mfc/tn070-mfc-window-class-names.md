---
title: 'テクニカル ノート 70: MFC のウィンドウ クラス名'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: ad43f5af5d2e90cb5fc2bc90f0909c2b495b4a4c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373486"
---
# <a name="tn070-mfc-window-class-names"></a>テクニカル ノート 70: MFC のウィンドウ クラス名

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

MFC ウィンドウでは、ウィンドウの機能を反映する動的に作成されたクラス名が使用されます。 MFC は、アプリケーションによって生成されるフレーム ウィンドウ、ビュー、およびポップアップ ウィンドウに対して、クラス名を動的に生成します。 MFC アプリケーションによって生成されるダイアログ ボックスとコントロールには、対象のウィンドウのクラスの Windows が指定した名前が付いています。

動的に指定されたクラス名を置き換えるには、独自のウィンドウ クラスを登録し[、PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)のオーバーライドで使用します。 MFC で提供されるクラス名は、次の 2 つの形式のいずれかに適合します。

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

`%x`文字を置き換える 16 進数の数字は[、WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)構造体のデータから入力されます。 MFC では、同一の**WNDCLASS**構造体を必要とする複数の C++ クラスが同じ登録済みウィンドウ クラスを共有できるように、この手法を使用します。 ほとんどの単純な Win32 アプリケーションとは異なり、MFC アプリケーションには**WNDPROC**が 1 つしかないので、時間とメモリを節約するために簡単に**WNDCLASS**構造体を共有できます。 上記の文字の`%x`置き換え可能な値は次のとおりです。

- **インスタンス**

- **スタイル**

- **カーソルを使用します。**

- **バックグラウンド**

- **アイコン**

最初のフォーム`Afx:%x:%x`( ) は **、hCursor**、 **hbrBackground**、および**hIcon**がすべて NULL の場合に使用**されます**。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)<br/>
[テクニカル ノート 20: ID 名および番号に関する規約](../mfc/tn020-id-naming-and-numbering-conventions.md)
