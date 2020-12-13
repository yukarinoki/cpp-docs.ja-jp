---
description: 詳細については、「CWindowImpl を使用したウィンドウの実装」を参照してください。
title: CWindowImpl を使用したウィンドウの実装
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: 4010450b21a7cbbb4c4f1e4b7a39f594ce1e466e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152882"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>CWindowImpl を使用したウィンドウの実装

ウィンドウを実装するには、からクラスを派生させ `CWindowImpl` ます。 派生クラスで、メッセージマップとメッセージハンドラー関数を宣言します。 これで、次の3つの方法でクラスを使用できるようになりました。

- [新しい Windows クラスに基づいてウィンドウを作成する](#_atl_creating_a_window_based_on_a_new_windows_class)

- [既存の Windows クラスをスーパークラスにする](#_atl_superclassing_an_existing_windows_class)

- [既存のウィンドウをサブクラス化する](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> 新しい Windows クラスに基づくウィンドウの作成

`CWindowImpl` Windows クラス情報を宣言するための [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) マクロを格納します。 このマクロは、 `GetWndClassInfo` [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) を使用して新しい Windows クラスの情報を定義する関数を実装します。 `CWindowImpl::Create`が呼び出されると、この Windows クラスは登録され、新しいウィンドウが作成されます。

> [!NOTE]
> `CWindowImpl` マクロに NULL を渡します `DECLARE_WND_CLASS` 。これは、ATL によって Windows クラス名が生成されることを意味します。 独自の名前を指定するには、から派生したクラスの DECLARE_WND_CLASS に文字列を渡し `CWindowImpl` ます。

## <a name="example-implement-a-window"></a>例: ウィンドウを実装する

新しい Windows クラスに基づいてウィンドウを実装するクラスの例を次に示します。

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

ウィンドウを作成するには、のインスタンスを作成 `CMyWindow` してから、メソッドを呼び出し `Create` ます。

> [!NOTE]
> 既定の Windows クラス情報をオーバーライドするには、 `GetWndClassInfo` `CWndClassInfo` メンバーを適切な値に設定して、派生クラスにメソッドを実装します。

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a> Superclassing 既存の Windows クラス

[DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass)マクロを使用すると、既存の Windows クラスをスーパークラスにするウィンドウを作成できます。 派生クラスでこのマクロを指定し `CWindowImpl` ます。 他の ATL ウィンドウと同様に、メッセージはメッセージマップによって処理されます。

DECLARE_WND_SUPERCLASS を使用すると、新しい Windows クラスが登録されます。 この新しいクラスは、指定した既存のクラスと同じになりますが、ウィンドウプロシージャは `CWindowImpl::WindowProc` (またはこのメソッドをオーバーライドする関数で) に置き換えられます。

## <a name="example-superclass-the-edit-class"></a>例: Edit クラスのスーパークラス

標準の Edit クラスをスーパークラスにするクラスの例を次に示します。

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

スーパークラス Edit ウィンドウを作成するには、のインスタンスを作成 `CMyEdit` してから、メソッドを呼び出し `Create` ます。

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a> 既存のウィンドウのサブクラス化

既存のウィンドウをサブクラス化するには、前の2つのケースのように、からクラスを派生させ、 `CWindowImpl` メッセージマップを宣言します。 ただし、既に存在するウィンドウをサブクラス化するため、Windows クラスの情報は指定しないことに注意してください。

を呼び出すので `Create` はなく、を呼び出し `SubclassWindow` て、サブクラス化する既存のウィンドウへのハンドルを渡します。 ウィンドウがサブクラス化されたら、 `CWindowImpl::WindowProc` (またはこのメソッドをオーバーライドする関数) を使用してメッセージをメッセージマップに送信します。 サブクラスウィンドウをオブジェクトからデタッチするには、を呼び出し `UnsubclassWindow` ます。 ウィンドウの元のウィンドウプロシージャが復元されます。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)
