---
title: クラスをプロパティページインプルします。
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
ms.openlocfilehash: ae64c212520510a443fbb2b8adc99243e8f8843a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330699"
---
# <a name="csnapinpropertypageimpl-class"></a>クラスをプロパティページインプルします。

このクラスには、スナップイン プロパティ ページ オブジェクトを実装するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティ ページ インプル::C スナップインプロパティ ページ インビプ](#csnapinpropertypageimpl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[閉じるには](#canceltoclose)|**[OK] ボタン**と [**キャンセル]** ボタンの状態を変更します。|
|[プロパティページインプル::作成](#create)|新しく作成`CSnapInPropertyPageImpl`されたオブジェクトを初期化します。|
|[プロパティページインプル::オンApply](#onapply)|ユーザーがウィザード型のプロパティ シートを使用しているときに [**今すぐ適用**] ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[プロパティページインプル::オンヘルプ](#onhelp)|ユーザーがウィザード型のプロパティ シートを使用しているときに **[ヘルプ**] ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[プロパティページインプル::オンキルアクティブ](#onkillactive)|現在のページがアクティブでなくなったときに、フレームワークによって呼び出されます。|
|[ページインプル::クエリキャンセル](#onquerycancel)|ユーザーが **[キャンセル]** ボタンをクリックしたとき、およびキャンセルが行われる前に、フレームワークによって呼び出されます。|
|[プロパティページインプル::オンリセット](#onreset)|ユーザーがウィザード型のプロパティ シートを使用しているときに [**リセット**] ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[プロパティページインプル::オンセットアクティブ](#onsetactive)|現在のページがアクティブになったときに、フレームワークによって呼び出されます。|
|[CSnapInプロパティページインプル::ウィザードバック](#onwizardback)|ユーザーがウィザード型のプロパティ シートを使用しているときに [**戻る**] ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[CSnapIn プロパティページインプル::ウィザード完了](#onwizardfinish)|ユーザーがウィザード型のプロパティ シートを使用しているときに **[完了]** ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[次のページインプジェクスト](#onwizardnext)|ユーザーがウィザード型のプロパティ シートを使用しているときに **[Next]** ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[プロパティページインプル::クエリ兄弟](#querysiblings)|現在のメッセージをプロパティ シートのすべてのページに転送します。|
|[プロパティページインプラクプッター::セット修正](#setmodified)|[**今すぐ適用**] ボタンをアクティブまたは非アクティブ化する場合に呼び出します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[プロパティページインプル::m_psp](#m_psp)|オブジェクトによって`PROPSHEETPAGE`使用される Windows`CSnapInPropertyPageImpl`構造体。|

## <a name="remarks"></a>解説

`CSnapInPropertyPageImpl`では、スナップイン プロパティ ページ オブジェクトの基本的な実装を提供します。 スナップイン プロパティ ページの基本的な機能は、いくつかの異なるインターフェイスとマップの種類を使用して実装されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsnap.h

## <a name="csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>閉じるには

モーダル プロパティ シートのページ内のデータに対して、回復不可能な変更が行われた後にこの関数を呼び出します。

```
void CancelToClose();
```

### <a name="remarks"></a>解説

この機能は **、[OK]** ボタンを **[閉じる**] に変更し、[**キャンセル**] ボタンを無効にします。 この変更により、変更が永続的であり、変更を取り消すことができないことがユーザーに警告されます。

モード`CancelToClose`レス プロパティ シートには既定で **[キャンセル]** ボタンがないため、メンバ関数はモードレス プロパティ シートでは何も行いません。

## <a name="csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>プロパティ ページ インプル::C スナップインプロパティ ページ インビプ

`CSnapInPropertyPageImpl` オブジェクトを構築します。

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszタイトル*<br/>
[in]プロパティ ページのタイトル。

### <a name="remarks"></a>解説

基になる構造を初期化するには[、CSnapInPropertyPageImpl::作成](#create)を呼び出します。

## <a name="csnapinpropertypageimplcreate"></a><a name="create"></a>プロパティページインプル::作成

プロパティ ページの基になる構造を初期化します。

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>戻り値

新しく作成された`PROPSHEETPAGE`プロパティ シートの属性を含む構造体へのハンドル。

### <a name="remarks"></a>解説

この関数を呼び出す前に、最初に[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)を呼び出す必要があります。

## <a name="csnapinpropertypageimplm_psp"></a><a name="m_psp"></a>プロパティページインプル::m_psp

`m_psp`は、 の特性をメンバーが格納`PROPSHEETPAGE`する構造体です。

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>解説

この構造体を使用して、プロパティ ページの構築後の外観を初期化します。

メンバーの一覧を含む、この構造体の詳細については、Windows SDK の[「PROPSHEETPAGE」](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v3)を参照してください。

## <a name="csnapinpropertypageimplonapply"></a><a name="onapply"></a>プロパティページインプル::オンApply

このメンバー関数は、ユーザーが **[OK]** または [**今すぐ適用**] ボタンをクリックしたときに呼び出されます。

```
BOOL OnApply();
```

### <a name="return-value"></a>戻り値

変更が受け入れられる場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

フレームワーク`OnApply`から呼び出す前に、そのパラメータを`SetModified`TRUE に呼び出して設定しておく必要があります。 これにより、ユーザーがプロパティ ページで変更を行うとすぐに [**今すぐ適用**] ボタンがアクティブになります。

ユーザーが **[今すぐ適用**] ボタンをクリックしたときにプログラムが実行する動作を指定するには、このメンバー関数をオーバーライドします。 オーバーライドする場合、関数は TRUE を返して変更を受け入れ、変更が有効にならないように FALSE を返します。

既定の実装では`OnApply`TRUE が返されます。

## <a name="csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>プロパティページインプル::オンヘルプ

このメンバー関数は、ユーザーがプロパティ ページの **[ヘルプ**] ボタンをクリックしたときに呼び出されます。

```
void OnHelp();
```

### <a name="remarks"></a>解説

プロパティ ページのヘルプを表示するには、このメンバー関数をオーバーライドします。

## <a name="csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>プロパティページインプル::オンキルアクティブ

このメンバー関数は、ページがアクティブ ページでなくなったときに呼び出されます。

```
BOOL OnKillActive();
```

### <a name="return-value"></a>戻り値

データが正常に更新された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

特殊なデータ検証タスクを実行するには、このメンバー関数をオーバーライドします。

## <a name="csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>ページインプル::クエリキャンセル

このメンバー関数は、ユーザーが **[キャンセル]** ボタンをクリックしたとき、およびキャンセル操作が行われる前に呼び出されます。

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>戻り値

キャンセル操作を許可する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ユーザーが **[キャンセル]** ボタンをクリックしたときにプログラムが実行するアクションを指定するには、このメンバー関数をオーバーライドします。

既定の実装では`OnQueryCancel`TRUE が返されます。

## <a name="csnapinpropertypageimplonreset"></a><a name="onreset"></a>プロパティページインプル::オンリセット

このメンバー関数は、ユーザーが **[キャンセル]** ボタンをクリックしたときに呼び出されます。

```
void OnReset();
```

### <a name="remarks"></a>解説

この関数が呼び出されると、ユーザーが [**今すぐ適用**] ボタンをクリックして行ったすべてのプロパティ ページへの変更は破棄され、プロパティ シートはフォーカスを保持します。

ユーザーが **[キャンセル]** ボタンをクリックしたときにプログラムが実行する動作を指定するには、このメンバー関数をオーバーライドします。

## <a name="csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>プロパティページインプル::オンセットアクティブ

このメンバー関数は、ユーザーがページを選択し、アクティブ ページになったときに呼び出されます。

```
BOOL OnSetActive();
```

### <a name="return-value"></a>戻り値

ページが正常にアクティブに設定された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ページがアクティブになったときにタスクを実行するには、このメンバー関数をオーバーライドします。 このメンバー関数をオーバーライドする場合は、他の処理が行われる前に、既定のバージョンを呼び出す必要があります。

既定の実装では TRUE が返されます。

## <a name="csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInプロパティページインプル::ウィザードバック

このメンバー関数は、ユーザーがウィザードの [**戻る**] ボタンをクリックしたときに呼び出されます。

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>戻り値

- 0 を指定すると、自動的に前のページに進みます。

- -1 ページが変更されないようにします。

次のページ以外のページにジャンプするには、表示するダイアログ ボックスの識別子を返します。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、戻**る**ボタンがクリックされたときにユーザーが実行する必要のあるアクションを指定します。

## <a name="csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapIn プロパティページインプル::ウィザード完了

このメンバー関数は、ユーザーがウィザードの **[完了**] ボタンをクリックしたときに呼び出されます。

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>戻り値

ウィザードの終了時にプロパティ シートが破棄された場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、ユーザーが **[完了]** ボタンをクリックしたときに実行する必要のある操作を指定します。

## <a name="csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>次のページインプジェクスト

このメンバー関数は、ユーザーがウィザードの [**次へ**] をクリックしたときに呼び出されます。

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>戻り値

- 自動的に次のページに進むには 0 を指定します。

- -1 ページが変更されないようにします。

次のページ以外のページにジャンプするには、表示するダイアログ ボックスの識別子を返します。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、ユーザーが [**次へ**] ボタンをクリックしたときに実行する必要のあるアクションを指定します。

## <a name="csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>プロパティページインプル::クエリ兄弟

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

メッセージを次のプロパティ ページに転送しない場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ページが 0 以外の値を返す場合、プロパティ シートはメッセージを後続のページに送信しません。

## <a name="csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>プロパティページインプラクプッター::セット修正

プロパティ ページの設定を適切な外部オブジェクトに適用するかどうかを基に **、[Apply Now]** ボタンを有効または無効にするには、このメンバー関数を呼び出します。

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>パラメーター

*b変更*<br/>
[in]プロパティ ページの設定が最後に適用されてから変更されたことを示す場合は TRUE。プロパティ ページの設定が適用されたことを示す場合は FALSE、または無視する必要があることを示します。

### <a name="remarks"></a>解説

プロパティ シートは、どのページが "ダーティ" か、つまり呼び出した`SetModified( TRUE )`プロパティ ページを追跡します。 いずれかのページを呼び出`SetModified( TRUE )`すと、[**今すぐ適用**] ボタンが常に有効になります。 [**今すぐ適用]** ボタンは、いずれかの`SetModified( FALSE )`ページを呼び出すときに無効になりますが、他のどのページも "ダーティ" ではない場合のみです。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
