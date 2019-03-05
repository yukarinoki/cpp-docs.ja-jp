---
title: CSnapInPropertyPageImpl クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
ms.openlocfilehash: d4e363f7de46de6f875a28a62d4ecdf929decdc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272175"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl クラス

このクラスは、スナップインのプロパティ ページ オブジェクトを実装するためのメソッドを提供します。

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
|[CSnapInPropertyPageImpl::OnApply](#onapply)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**今すぐ適用**ウィザード型のプロパティ シートを使用しているときにボタンをクリックします。|
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**ヘルプ**ウィザード型のプロパティ シートを使用しているときにボタンをクリックします。|
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|現在のページがアクティブでなくなったときに、フレームワークによって呼び出されます。|
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**キャンセル**ボタンと、キャンセルが行われる前にします。|
|[CSnapInPropertyPageImpl::OnReset](#onreset)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**リセット**ウィザード型のプロパティ シートを使用しているときにボタンをクリックします。|
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|現在のページがアクティブになったときに、フレームワークによって呼び出されます。|
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**戻る**ウィザード型のプロパティ シートを使用しているときにボタンをクリックします。|
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**完了**ウィザード型のプロパティ シートを使用しているときにボタンをクリックします。|
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**次**ウィザード型のプロパティ シートを使用しているときにボタンをクリックします。|
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|プロパティ シートのすべてのページには、現在のメッセージを転送します。|
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|アクティブ化または非アクティブ化を呼び出し、**今すぐ適用**ボタンをクリックします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows`PROPSHEETPAGE`構造で使用される、`CSnapInPropertyPageImpl`オブジェクト。|

## <a name="remarks"></a>Remarks

`CSnapInPropertyPageImpl` スナップインのプロパティ ページのオブジェクトの基本的な実装を提供します。 スナップインのプロパティ ページの基本機能は、複数のインターフェイスを使用して実装し、型をマップします。

## <a name="inheritance-hierarchy"></a>継承階層

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsnap.h

##  <a name="canceltoclose"></a>  CSnapInPropertyPageImpl::CancelToClose

モーダル プロパティ シートのページ内のデータに、回復不可能な変更が行われた後は、この関数を呼び出します。

```
void CancelToClose();
```

### <a name="remarks"></a>Remarks

この関数が変更されます、 **OK**ボタンを**閉じる**を無効にして、**キャンセル**ボタン。 これは、変更、アラートの変更が確定され、変更があるユーザーを取り消すことができません。

`CancelToClose`モードレス プロパティ シートがないため、メンバー関数は、モードレス プロパティ シートでは nothing を**キャンセル**既定ではボタンをクリックします。

##  <a name="csnapinpropertypageimpl"></a>  CSnapInPropertyPageImpl::CSnapInPropertyPageImpl

`CSnapInPropertyPageImpl` オブジェクトを構築します。

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszTitle*<br/>
[in]プロパティ ページのタイトル。

### <a name="remarks"></a>Remarks

基になる構造を初期化するために呼び出す[CSnapInPropertyPageImpl::Create](#create)します。

##  <a name="create"></a>  CSnapInPropertyPageImpl::Create

この関数では、プロパティ ページの基になる構造体を初期化します。

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>戻り値

識別するハンドルを`PROPSHEETPAGE`新しく作成されたプロパティ シートの属性を含む構造体。

### <a name="remarks"></a>Remarks

呼び出す必要がありますまず[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)この関数を呼び出す前にします。

##  <a name="m_psp"></a>  CSnapInPropertyPageImpl::m_psp

`m_psp` メンバーの特性を格納する構造体は、`PROPSHEETPAGE`します。

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Remarks

この構造体を使用して、構築した後、プロパティ ページの外観を初期化します。

そのメンバーの一覧を含む、この構造の詳細については、次を参照してください。 [PROPSHEETPAGE](https://msdn.microsoft.com/library/aa815151) Windows SDK に含まれています。

##  <a name="onapply"></a>  CSnapInPropertyPageImpl::OnApply

ユーザーがクリックしたときに、このメンバー関数が呼び出されます、 **OK**または**今すぐ適用**ボタンをクリックします。

```
BOOL OnApply();
```

### <a name="return-value"></a>戻り値

変更が受け付けられた場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

前に`OnApply`呼び出すことができます、フレームワークによってする必要がありますが呼び出さ`SetModified`し、そのパラメーターを TRUE に設定します。 これは、ライセンス認証、**今すぐ適用**ユーザーは、プロパティ ページで変更を行うとすぐにボタンをクリックします。

ユーザーがクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライド、**今すぐ適用**ボタンをクリックします。 オーバーライドする場合、変更を反映する場合は TRUE と FALSE を有効になってからの変更を防ぐために、関数を返します。

既定の実装`OnApply`TRUE を返します。

##  <a name="onhelp"></a>  CSnapInPropertyPageImpl::OnHelp

ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**ヘルプ**プロパティ ページのボタンをクリックします。

```
void OnHelp();
```

### <a name="remarks"></a>Remarks

プロパティ ページのヘルプを表示するには、このメンバー関数をオーバーライドします。

##  <a name="onkillactive"></a>  CSnapInPropertyPageImpl::OnKillActive

このメンバー関数は、ページがアクティブでなくなったときに呼び出されます。

```
BOOL OnKillActive();
```

### <a name="return-value"></a>戻り値

データが正常に更新された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

特別なデータの検証タスクを実行するには、このメンバー関数をオーバーライドします。

##  <a name="onquerycancel"></a>  CSnapInPropertyPageImpl::OnQueryCancel

このメンバー関数は、ユーザーがクリックしたときに、**キャンセル**ボタンをクリックし、動作が発生した、キャンセルする前にします。

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>戻り値

0 以外の場合、キャンセル操作を許可するにはそれ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

ユーザーがクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライド、**キャンセル**ボタンをクリックします。

既定の実装`OnQueryCancel`TRUE を返します。

##  <a name="onreset"></a>  CSnapInPropertyPageImpl::OnReset

ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**キャンセル**ボタンをクリックします。

```
void OnReset();
```

### <a name="remarks"></a>Remarks

この関数が呼び出されたときにをクリックして、ユーザーによって行われたすべてのプロパティ ページに変更、**今すぐ適用**ボタンは破棄され、プロパティ シートにフォーカスが保持されます。

ユーザーがクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライド、**キャンセル**ボタンをクリックします。

##  <a name="onsetactive"></a>  CSnapInPropertyPageImpl::OnSetActive

ページは、ユーザーが選択され、アクティブになったときに呼び出されます。

```
BOOL OnSetActive();
```

### <a name="return-value"></a>戻り値

ページを正常にアクティブに設定されている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

ページがアクティブになったときにタスクを実行するには、このメンバー関数をオーバーライドします。 このメンバー関数のオーバーライドは、他の処理が行われる前に、既定のバージョンを呼び出す必要があります。

既定の実装では、TRUE を返します。

##  <a name="onwizardback"></a>  CSnapInPropertyPageImpl::OnWizardBack

ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**戻る**ウィザードのボタンをクリックします。

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>戻り値

- 前のページに切り替えが自動的に 0 を返します。

- ページの変更を防ぐためには-1。

次の 1 つ以外のページにジャンプするには、表示されるダイアログ ボックスの識別子を返します。

### <a name="remarks"></a>Remarks

何らかのアクションをユーザーには、ときに実行する必要がありますを指定するには、このメンバー関数をオーバーライド、**戻る**ボタンをクリックします。

##  <a name="onwizardfinish"></a>  CSnapInPropertyPageImpl::OnWizardFinish

ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**完了**ウィザードのボタンをクリックします。

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>戻り値

0 以外の場合、ウィザードが完了したら; プロパティ シートが破棄される場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

何らかのアクションをユーザーには、ときに実行する必要がありますを指定するには、このメンバー関数をオーバーライド、**完了**ボタンをクリックします。

##  <a name="onwizardnext"></a>  CSnapInPropertyPageImpl::OnWizardNext

ユーザーがクリックしたときに、このメンバー関数が呼び出されます、 **[次へ]** ウィザードのボタンをクリックします。

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>戻り値

- 次のページに切り替えが自動的に 0 を返します。

- ページの変更を防ぐためには-1。

次の 1 つ以外のページにジャンプするには、表示されるダイアログ ボックスの識別子を返します。

### <a name="remarks"></a>Remarks

何らかのアクションをユーザーには、ときに実行する必要がありますを指定するには、このメンバー関数をオーバーライド、**次**ボタンをクリックします。

##  <a name="querysiblings"></a>  CSnapInPropertyPageImpl::QuerySiblings

プロパティ シートの各ページにメッセージを転送するには、このメンバー関数を呼び出します。

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*wParam*<br/>
[in]メッセージに依存する追加情報を指定します。

*lParam*<br/>
[in]メッセージに依存する追加情報を指定します。

### <a name="return-value"></a>戻り値

以外の場合は、メッセージは、次のプロパティ ページに転送しない必要があります。それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

ページが 0 以外の値を返す場合、プロパティ シートは後続のページにメッセージを送信しません。

##  <a name="setmodified"></a>  CSnapInPropertyPageImpl::SetModified

有効または無効にするには、このメンバー関数を呼び出して、**今すぐ適用**適切な外部オブジェクトにプロパティ ページの設定を適用するかどうかに基づいて、ボタンをクリックします。

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>パラメーター

*bChanged*<br/>
[in]前回適用された後、プロパティ ページの設定が変更されていることを指定する場合は TRUEプロパティ ページの設定が適用されているか、無視するかを示す場合は FALSE。

### <a name="remarks"></a>Remarks

プロパティ シート ページの「ダーティ」、つまり追跡、呼び出した対象のプロパティ ページを保持する`SetModified( TRUE )`します。 **今すぐ適用**を呼び出す場合、ボタンが有効常に`SetModified( TRUE )`ページのいずれか。 **今すぐ適用**を呼び出すと、ボタンは無効になります`SetModified( FALSE )`のみ場合のどの他のページは「ダーティ」、ページの 1 つの

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
