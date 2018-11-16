---
title: 'テクニカル ノート 70: MFC のウィンドウ クラス名'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.classes
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: 609cfade60b1b7b51fb2fd5597c4d491d3eb861c
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692666"
---
# <a name="tn070-mfc-window-class-names"></a>テクニカル ノート 70: MFC のウィンドウ クラス名

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

MFC windows では、ウィンドウの機能を反映する動的に作成されたクラス名を使用します。 MFC には、フレーム ウィンドウ、ビュー、およびアプリケーションによって生成されたポップアップ ウィンドウの動的にクラス名が生成されます。 ダイアログ ボックスおよび MFC アプリケーションによって生成されたコントロールの対象のウィンドウ クラスの Windows が指定した名前であります。

独自のウィンドウ クラスを登録およびのオーバーライドで使用することで、動的に指定されたクラス名を置き換えることができます[PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)します。 それに MFC が指定したクラス名を使用して、2 つの形式を次のいずれかに一致します。

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

16 進の数字を置き換える、`%x`からのデータの文字が入力、 [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa)構造体。 MFC は、この手法を使用してように同じを必要とする複数の C++ クラス**WNDCLASS**構造体は、同じ登録されているウィンドウ クラスを共有できます。 ほとんどの単純な Win32 アプリケーションとは異なり MFC アプリケーションがある 1 つだけ**WNDPROC**簡単に共有できるように、 **WNDCLASS**時間とメモリを節約する構造体。 値に置き換え、`%x`文字の前に示したは次のようにします。

- **WNDCLASS.hInstance**

- **WNDCLASS.style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrBackground**

- **WNDCLASS.hIcon**

最初のフォーム (`Afx:%x:%x`) ときに使用される**hCursor**、 **hbrBackground**、および**hIcon**はすべて**NULL**します。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)<br/>
[テクニカル ノート 20: ID 名および番号に関する規約](../mfc/tn020-id-naming-and-numbering-conventions.md)

