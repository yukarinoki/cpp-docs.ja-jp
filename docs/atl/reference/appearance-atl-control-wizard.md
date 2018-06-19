---
title: 外観、ATL コントロール ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1d27b46f529d8423bdaf733928a9f3e46b3f185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358603"
---
# <a name="appearance-atl-control-wizard"></a>外観、ATL コントロール ウィザード
「検索結果」の概要をここに挿入します。  
  
 ウィザードのこのページを使用すると、コントロールの追加のユーザーの要素のオプションを識別できます。 このページとして識別されたコントロールで利用可能**標準コントロール**下にある**コントロール型**で、[オプション、ATL コントロール ウィザード](../../atl/reference/options-atl-control-wizard.md)ページ。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **状態の表示**  
 コンテナー内のコントロールの外観を設定します。  
  
-   **不透明な**: セット、`VIEWSTATUS_OPAQUE`ビット、[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)列挙体を描画するコントロール全体の四角形が渡される、 [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw)メソッドです。 コントロールが完全に不透明が表示され、コントロールの境界の背後にあるコンテナーのいずれも示しています。  
  
     この設定によりより迅速にコントロールを描画するコンテナーです。 このオプションが選択されていない場合、コントロールは透明な部分を含めることができます。  
  
     不透明なコントロールのみ純色の背景ことができます。  
  
-   セット、`VIEWSTATUS_SOLIDBKGND`ビット、`VIEWSTATUS`列挙します。 コントロールの背景は、パターンのない純色として表示されます。  
  
     このオプションは使用可能な場合にのみ、**不透明**オプションも選択します。  
  
 **コントロールを追加します。**  
 コントロールを追加して、Windows のコントロール型に基づく設定、 [CContainedWindow](ccontainedwindowt-class.md)コントロールを実装するクラスのデータ メンバーです。 また、メッセージ マップとコントロールの Windows メッセージを処理するメッセージ ハンドラー関数を追加します。 存在する場合は、作成する Windows コントロールの種類を一覧から選択します。  

  
-   `Button`  
  
-   `ListBox`  
  
-   `SysAnimate32`  
  
-   `SysListView32`  
  
-   `ComboBox`  
  
-   `RichEdit`  
  
-   `SysDateTimePick32`  
  
-   `SysMonthCal32`  
  
-   `ComboBoxEx32`  
  
-   `ScrollBar`  
  
-   `SysHeader32`  
  
-   `SysTabControl32`  
  
-   `Edit`  
  
-   `Static`  
  
-   `SysIPAddress32`  
  
-   `SysTreeView32`  
  
 **その他の状態**  
 コントロールの外観と動作の追加オプションを設定します。  
  
-   **実行時に非表示**: を表示しない実行時にコントロールを設定します。 非表示のコントロールを使用して、指定された間隔でイベントを発生させるなど、バック グラウンドで操作を実行することができます。  
  
-   **ボタンのように動作**: セット、`OLEMISC_ACTSLIKEBUTTON`ビット、[入ります](http://msdn.microsoft.com/library/windows/desktop/ms678497)機能するコントロールを有効にする列挙体などのボタンをクリックします。 場合は、コンテナーには、既定のボタンとコントロールのクライアント サイトがマークされているが、太いフレーム自体の描画による既定のボタンとして表示するボタン コントロールを有効には、このオプションを選択します。 参照してください[CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault)詳細についてはします。  
  
-   **ラベルのように動作**: セット、`OLEMISC_ACTSLIKELABEL`ビット、`OLEMISC`置換するコントロールをコンテナーのネイティブのラベルを有効にする列挙です。 コンテナーは、何もの場合、このフラグを行うにはどのようなを決定します。  
  
 **その他**  
 コントロールの他の動作のオプションを設定します。  
  
-   **DC の正規化**: 自体の描画に呼び出された場合は、正規化されたデバイス コンテキストを作成するコントロールを設定します。 コントロールの外観を標準化します。 この操作が、描画の効率が低下します。  
  
-   **ウィンドウのみ**: ウィンドウレス コントロールであることを指定します。 このオプションを選択しない場合、コントロールはウィンドウなしのオブジェクトをサポートするコンテナーで自動的にウィンドウなしありウィンドウなしのオブジェクトをサポートしていないコンテナーで自動的にウィンドウです。 このオプションを選択するように強制、ウィンドウなしのオブジェクトをサポートするコンテナーであっても、ウィンドウをでしょう。  
  
-   **挿入可能な**: このオプションを選択するコントロールに表示される、**オブジェクトの挿入**Word や Excel などのアプリケーションのダイアログ ボックス。 コントロールは、このダイアログ ボックスを使用して埋め込みオブジェクトをサポートする任意のアプリケーションで挿入できます。  
  
## <a name="see-also"></a>関連項目  
 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)   
 [サンプルを SUBEDIT: スーパークラス標準の Windows コントロール](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)

