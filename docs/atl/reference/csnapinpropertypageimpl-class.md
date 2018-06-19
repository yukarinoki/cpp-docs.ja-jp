---
title: CSnapInPropertyPageImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13714553bdf926b00bd4dd76e039d89c7f78f959
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366144"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl クラス
このクラスは、スナップインからプロパティ ページ オブジェクトを実装するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|状態を変更、 **OK**と**キャンセル**ボタン。|  
|[CSnapInPropertyPageImpl::Create](#create)|新しく作成した初期化`CSnapInPropertyPageImpl`オブジェクト。|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**今すぐ適用**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**ヘルプ**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|現在のページがアクティブでなくなったときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**キャンセル**ボタンをクリックし、キャンセルが行われる前にします。|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**リセット**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|現在のページがアクティブになったときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**戻る**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**完了**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、`Next`ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|プロパティ シートのすべてのページに現在のメッセージを転送します。|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|アクティブ化または非アクティブ化の呼び出し、**今すぐ適用**ボタンをクリックします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE**構造で使用される、`CSnapInPropertyPageImpl`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CSnapInPropertyPageImpl` スナップイン プロパティ ページ オブジェクトの基本的な実装を提供します。 スナップイン プロパティ ページの基本機能は、複数のインターフェイスを使用して実装し、型をマップします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsnap.h  
  
##  <a name="canceltoclose"></a>  CSnapInPropertyPageImpl::CancelToClose  
 モーダル プロパティ シートのページ内のデータを回復できない変更が行われた後は、この関数を呼び出します。  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>コメント  
 この関数が変更されます、 **OK**  ボタンをクリックして**閉じる**を無効にして、**キャンセル**ボタンをクリックします。 これは、アラートの変更が確定され、変更があるユーザーはキャンセルできませんを変更します。  
  
 `CancelToClose`メンバー関数は、モードレス プロパティ シートでは nothing モードレス プロパティ シートがあるないため、**キャンセル**既定ボタンをクリックします。  
  
##  <a name="csnapinpropertypageimpl"></a>  CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 `CSnapInPropertyPageImpl` オブジェクトを構築します。  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTitle`  
 [in]プロパティ ページのタイトル。  
  
### <a name="remarks"></a>コメント  
 基になる構造を初期化するために呼び出す[CSnapInPropertyPageImpl::Create](#create)です。  
  
##  <a name="create"></a>  CSnapInPropertyPageImpl::Create  
 この関数では、プロパティ ページの基になる構造体を初期化します。  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>戻り値  
 ハンドル、 **PROPSHEETPAGE**新しく作成されたプロパティ シートの属性を含む構造体。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要がありますまず[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)この関数を呼び出す前にします。  
  
##  <a name="m_psp"></a>  CSnapInPropertyPageImpl::m_psp  
 `m_psp` 構造体メンバーの格納の特性は、 **PROPSHEETPAGE**です。  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>コメント  
 この構造体を使用して、構築した後、プロパティ ページの外観を初期化します。  
  
 そのメンバーの一覧を含めて、この構造の詳細についてを参照してください。 [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) Windows SDK に含まれています。  
  
##  <a name="onapply"></a>  CSnapInPropertyPageImpl::OnApply  
 このメンバー関数は、ユーザーがクリックしたときに、 **OK**または**今すぐ適用**ボタンをクリックします。  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>戻り値  
 変更が受け付けられた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 前に`OnApply`呼び出すことができます、フレームワークによってする必要がありますが呼び出さ`SetModified`そのパラメーターを設定および**TRUE**です。 これは、ライセンス認証、**今すぐ適用**プロパティ ページで、ユーザーによって変更するとすぐにボタンをクリックします。  
  
 ユーザーがクリックしたときのプログラムの動作を指定するには、この関数をオーバーライドします**今すぐ適用**ボタンをクリックします。 をオーバーライドする関数で返す必要があります**TRUE**の変更を確定と**FALSE**変更反映されないようにします。  
  
 既定の実装`OnApply`返します**TRUE**です。  
  
##  <a name="onhelp"></a>  CSnapInPropertyPageImpl::OnHelp  
 このメンバー関数は、ユーザーがクリックしたときに、**ヘルプ**プロパティ ページのボタンをクリックします。  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>コメント  
 プロパティ ページのヘルプを表示するには、このメンバー関数をオーバーライドします。  
  
##  <a name="onkillactive"></a>  CSnapInPropertyPageImpl::OnKillActive  
 ページがアクティブでなくなったときに呼び出されます。  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>戻り値  
 データが正常に更新された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 特別なデータの検証タスクを実行するには、このメンバー関数をオーバーライドします。  
  
##  <a name="onquerycancel"></a>  CSnapInPropertyPageImpl::OnQueryCancel  
 このメンバー関数は、ユーザーがクリックしたときに、**キャンセル**ボタンをクリックし、キャンセルする前にアクションが行われる。  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>戻り値  
 キャンセル操作を許可するのには 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーがクリックしたときのプログラムの動作を指定するには、この関数をオーバーライド、**キャンセル**ボタンをクリックします。  
  
 既定の実装`OnQueryCancel`返します**TRUE**です。  
  
##  <a name="onreset"></a>  CSnapInPropertyPageImpl::OnReset  
 このメンバー関数は、ユーザーがクリックしたときに、**キャンセル**ボタンをクリックします。  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>コメント  
 クリックして、ユーザーによって加えられたすべてのプロパティ ページにこの関数が呼び出されると、変更、**今すぐ適用**ボタンは破棄され、プロパティ シートにフォーカスが保持されます。  
  
 ユーザーがクリックしたときのプログラムの動作を指定するには、この関数をオーバーライド、**キャンセル**ボタンをクリックします。  
  
##  <a name="onsetactive"></a>  CSnapInPropertyPageImpl::OnSetActive  
 ページは、ユーザーが選択され、アクティブになったときに呼び出されます。  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>戻り値  
 ページを正常にアクティブに設定されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ページがアクティブになったときにタスクを実行するには、このメンバー関数をオーバーライドします。 このメンバー関数のオーバーライドは、他の処理が行われる前に、既定のバージョンを呼び出す必要があります。  
  
 既定の実装を返します**TRUE**です。  
  
##  <a name="onwizardback"></a>  CSnapInPropertyPageImpl::OnWizardBack  
 このメンバー関数は、ユーザーがクリックしたときに、**戻る**ウィザードのボタンをクリックします。  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>戻り値  
  
-   前のページ切り替えが自動的に 0 を返します。  
  
-   ページを変更できないようにする-1 です。  
  
 次の 1 つ以外のページにジャンプするには、表示されるダイアログ ボックスの識別子を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーには、ときに実行する必要がいくつかのアクションを指定するには、このメンバー関数をオーバーライド、**戻る**ボタンをクリックします。  
  
##  <a name="onwizardfinish"></a>  CSnapInPropertyPageImpl::OnWizardFinish  
 このメンバー関数は、ユーザーがクリックしたときに、**完了**ウィザードのボタンをクリックします。  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが、ウィザードが終了したときに破棄される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーには、ときに実行する必要がいくつかのアクションを指定するには、このメンバー関数をオーバーライド、**完了**ボタンをクリックします。  
  
##  <a name="onwizardnext"></a>  CSnapInPropertyPageImpl::OnWizardNext  
 このメンバー関数は、ユーザーがクリックしたときに、`Next`ウィザードのボタンをクリックします。  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>戻り値  
  
-   次のページに切り替えが自動的に 0 を返します。  
  
-   ページを変更できないようにする-1 です。  
  
 次の 1 つ以外のページにジャンプするには、表示されるダイアログ ボックスの識別子を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーには、ときに実行する必要がいくつかのアクションを指定するには、このメンバー関数をオーバーライド、`Next`ボタンをクリックします。  
  
##  <a name="querysiblings"></a>  CSnapInPropertyPageImpl::QuerySiblings  
 プロパティ シートの各ページにメッセージを転送するには、このメンバー関数を呼び出します。  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `wParam`  
 [in]追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 [in]追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 次のプロパティ ページにメッセージを転送するかいない場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ページが 0 以外の値を返す場合、プロパティ シートは後続のページにメッセージを送信しません。  
  
##  <a name="setmodified"></a>  CSnapInPropertyPageImpl::SetModified  
 有効または無効にするには、このメンバー関数を呼び出す、**今すぐ適用**、適切な外部のオブジェクトにプロパティ ページの設定を適用する必要があるかどうかに基づいてボタンをクリックします。  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bChanged`  
 [in]**TRUE**プロパティ ページの設定が適用されたか、前回以降変更されていることを示すために**FALSE**プロパティ ページの設定が適用されているか、無視するかを示します。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートをページは「ダーティ」、つまり追跡、呼び出した対象のプロパティ ページを保持**SetModified (TRUE)** です。 **今すぐ適用**ボタンは常に有効にするを呼び出す場合**SetModified (TRUE)** ページのいずれか。 **今すぐ適用**を呼び出すと、ボタンは無効になります**SetModified (FALSE)** のみ場合、その他のページの [なし] は「ダーティ」ですが、ページの 1 つの  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
