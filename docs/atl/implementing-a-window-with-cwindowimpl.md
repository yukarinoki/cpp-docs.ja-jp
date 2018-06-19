---
title: CWindowImpl のウィンドウを実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CWindowImpl
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9c1fc32d2265f6853c4dd34a3eb463609fca52b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356548"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>CWindowImpl のウィンドウの実装
ウィンドウを実装するのには、派生クラスを`CWindowImpl`です。 派生クラスでは、メッセージ マップとメッセージ ハンドラー関数を宣言します。 これで、3 つの方法で、クラスを使用することができます。  
  
-   [新しい Windows クラスに基づいてウィンドウを作成します。](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [既存のウィンドウ クラスをスーパークラス](#_atl_superclassing_an_existing_windows_class)  
  
-   [既存のウィンドウをサブクラス化](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> 新しい Windows クラスに基づいてウィンドウを作成します。  
 `CWindowImpl` 含まれています、 [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class)ウィンドウ クラスの情報を宣言するマクロです。 このマクロを実装して、`GetWndClassInfo`を使用して関数を[CWndClassInfo](../atl/reference/cwndclassinfo-class.md)新しいウィンドウ クラスの情報を定義します。 ときに`CWindowImpl::Create`が呼び出されると、この Windows クラスが登録されているし、新しいウィンドウを作成します。  
  
> [!NOTE]
>  `CWindowImpl` 渡します**NULL**を`DECLARE_WND_CLASS`マクロで、ATL は Windows クラス名を生成することを意味します。 自分の名前を指定する文字列を渡す`DECLARE_WND_CLASS`で、 `CWindowImpl`-クラスを派生します。  
  
## <a name="example"></a>例  
 新しい Windows クラスに基づいて、ウィンドウを実装するクラスの例を次に示します。  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]  
  
 インスタンスを作成ウィンドウを作成するには、`CMyWindow`を呼び出すと、**作成**メソッドです。  
  
> [!NOTE]
>  既定の Windows クラス情報をオーバーライドするには、実装、`GetWndClassInfo`を設定して、派生クラスでメソッド、`CWndClassInfo`メンバーを適切な値です。  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a> 既存のウィンドウ クラスをスーパークラス化  
 [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass)マクロを使用すると、ウィンドウをスーパークラス化する既存のウィンドウを作成するクラス。 このマクロを指定して、 `CWindowImpl`-クラスを派生します。 その他の ATL ウィンドウと同様に、メッセージは、メッセージ マップによって処理されます。  
  
 使用すると`DECLARE_WND_SUPERCLASS`、新しいウィンドウ クラスが登録されます。 この新しいクラスには、既存のクラスを指定するが、ウィンドウ プロシージャを置き換えると同じである、 `CWindowImpl::WindowProc` (または、このメソッドをオーバーライドする関数を使用)。  
  
## <a name="example"></a>例  
 次の例に示しますクラスをスーパークラス化する、標準的な編集クラス。  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]  
  
 スーパークラスの編集ウィンドウを作成するには、インスタンスを作成`CMyEdit`を呼び出すと、**作成**メソッドです。  
  
##  <a name="_atl_subclassing_an_existing_window"></a> 既存のウィンドウをサブクラス化  
 既存のウィンドウをサブクラス化からクラスを派生`CWindowImpl`し、2 つの以前の場合と同様に、メッセージ マップを宣言します。 ただし、サブクラス化するため既存のウィンドウのウィンドウ クラスの情報を指定しないことに注意してください。  
  
 呼び出す代わりに**作成**、呼び出す`SubclassWindow`サブクラスにする既存のウィンドウに、ハンドルを渡すことです。 使用するウィンドウをサブクラスと`CWindowImpl::WindowProc`(または、このメソッドをオーバーライドする関数)、メッセージ マップへのメッセージを送信するためです。 オブジェクトからウィンドウをサブクラス化をデタッチするには、呼び出す`UnsubclassWindow`です。 ウィンドウの元のウィンドウ プロシージャは復元されます。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの実装](../atl/implementing-a-window.md)

