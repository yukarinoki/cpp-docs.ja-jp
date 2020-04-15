---
title: ウィンドウを実装する
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: e5fdbf15ddd7edc69f0667a9b7e08c7c5e531a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319450"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>ウィンドウを実装する

ウィンドウを実装するには、 から`CWindowImpl`クラスを派生させます。 派生クラスで、メッセージ マップとメッセージ ハンドラー関数を宣言します。 クラスを使用するには、次の 3 つの方法があります。

- [新しい Windows クラスに基づいてウィンドウを作成する](#_atl_creating_a_window_based_on_a_new_windows_class)

- [既存の Windows クラスをスーパークラス化する](#_atl_superclassing_an_existing_windows_class)

- [既存のウィンドウをサブクラス化する](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a>新しいウィンドウ クラスに基づくウィンドウの作成

`CWindowImpl`には、Windows クラス情報を宣言する[DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class)マクロが含まれています。 このマクロは、新`GetWndClassInfo`しい Windows クラスの情報を定義するのに[CWndClassInfo](../atl/reference/cwndclassinfo-class.md)を使用する関数を実装します。 呼`CWindowImpl::Create`び出されると、この Windows クラスが登録され、新しいウィンドウが作成されます。

> [!NOTE]
> `CWindowImpl`マクロに NULL`DECLARE_WND_CLASS`を渡します。 独自の名前を指定するには、派生クラスのDECLARE_WND_CLASSに文字列`CWindowImpl`を渡します。

## <a name="example"></a>例

新しい Windows クラスに基づいてウィンドウを実装するクラスの例を次に示します。

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

ウィンドウを作成するには、のインスタンスを作成`CMyWindow`し、メソッドを`Create`呼び出します。

> [!NOTE]
> 既定の Windows クラス情報をオーバーライドするには`GetWndClassInfo`、メンバーを適切な値に設定`CWndClassInfo`して、派生クラスにメソッドを実装します。

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a>既存の Windows クラスのスーパークラス化

[DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass)マクロを使用すると、既存の Windows クラスをスーパークラス化するウィンドウを作成できます。 派生クラスでこのマクロを`CWindowImpl`指定します。 他の ATL ウィンドウと同様に、メッセージはメッセージ マップによって処理されます。

DECLARE_WND_SUPERCLASSを使用すると、新しい Windows クラスが登録されます。 この新しいクラスは、指定した既存のクラスと同じですが、ウィンドウ プロシージャを`CWindowImpl::WindowProc`(またはこのメソッドをオーバーライドする関数) に置き換えます。

## <a name="example"></a>例

標準の Edit クラスをスーパークラス化するクラスの例を次に示します。

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

スーパークラス化された編集ウィンドウを作成するには、インスタンスを作成`CMyEdit`してからメソッドを`Create`呼び出します。

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a>既存ウィンドウのサブクラス化

既存のウィンドウをサブクラス化するには、前の`CWindowImpl`2 つのケースのように、クラスを派生させ、メッセージ マップを宣言します。 ただし、既存のウィンドウをサブクラス化するため、Windows クラス情報は指定しません。

を呼び`Create`出す`SubclassWindow`代わりに、サブクラス化する既存のウィンドウにハンドルを呼び出して渡します。 ウィンドウがサブクラス化されると、メッセージ マップに`CWindowImpl::WindowProc`メッセージを送信するために、このメソッドをオーバーライドする関数を使用します。 サブクラス化されたウィンドウをオブジェクトからデタッチするには、`UnsubclassWindow`を呼び出します。 ウィンドウの元のウィンドウ プロシージャが復元されます。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)
