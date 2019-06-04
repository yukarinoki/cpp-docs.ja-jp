---
title: CWinFormsControl クラス
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: c1c7a394317fefba7911e9500126919e83389f20
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504662"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl クラス

Windows フォーム コントロールのホスティング用の基本機能を提供します。

## <a name="syntax"></a>構文

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>パラメーター

*TManagedControl*<br/>
MFC アプリケーションに表示される .NET Framework Windows フォーム コントロール。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows フォーム コントロールのラッパー オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|MFC コンテナーには、Windows フォーム コントロールを作成します。|
|[CWinFormsControl::GetControl](#getcontrol)|Windows フォーム コントロールへのポインターを取得します。|
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows フォーム コントロールを識別するハンドルを取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CWinFormsControl::operator -&gt;](#operator_-_gt)|置換[CWinFormsControl::GetControl](#getcontrol)式で。|
|[CWinFormsControl::operator TManagedControl^](#operator_tmanagedcontrol)|Windows フォーム コントロールへのポインターとして型をキャストします。|

## <a name="remarks"></a>Remarks

`CWinFormsControl`クラスには、Windows フォーム コントロールをホストするための基本的な機能が用意されています。

Windows フォームの使用に関する詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。

MFC コードは、ウィンドウ ハンドルをキャッシュする必要があります (通常に格納されている`m_hWnd`)。 一部の Windows フォーム コントロールのプロパティを必要とする、基になる Win32`Window`が破棄され、使用して再作成`DestroyWindow`と`CreateWindow`します。 MFC Windows フォームの実装のハンドル、`Destroy`と`Create`を更新するコントロールのイベント、`m_hWnd`メンバー。

> [!NOTE]
>  MFC Windows フォームの統合は、(AFXDLL が定義されている) MFC と動的にリンクするプロジェクトでのみ動作します。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h

##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl

MFC コンテナーには、Windows フォーム コントロールを作成します。

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>パラメーター

*pType*<br/>
作成するコントロールのデータ型。 必要があります、[型](/dotnet/api/system.type)データ型。

*dwStyle*<br/>
コントロールに適用するウィンドウ スタイル。 組み合わせを指定[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。 現時点では、次のスタイルのみがサポートされています。WS_TABSTOP、WS_VISIBLE、WS_DISABLED および WS_GROUP します。

*rect*<br/>
A [RECT 構造体](/windows/desktop/api/windef/ns-windef-tagrect)コントロールの左上隅および右下隅の座標を定義する (最初のオーバー ロードのみ)。

*nPlaceHolderID*<br/>
静的なプレース ホルダー コントロールのハンドルでは、リソース エディターで配置されます。 新しく作成された Windows フォーム コントロールの位置、z オーダーとスタイルと仮定すると、スタティック コントロールが置き換えられます (2 つ目のオーバー ロードのみ)。

*pParentWnd*<br/>
親ウィンドウへのポインター。

*nID*<br/>
新しく作成されたコントロールに割り当てられるリソースの ID 番号。

*pControl*<br/>
関連付けられる Windows フォーム コントロールのインスタンス、 [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md)オブジェクト (4 番目のオーバー ロードだけ)。

### <a name="return-value"></a>戻り値

成功した場合は、0 以外の値を返します。 失敗した場合は、0 を返します。

### <a name="remarks"></a>Remarks

このメソッドは、MFC コンテナーで .NET Framework Windows フォーム コントロールをインスタンス化します。

メソッドの最初のオーバー ロードは、.NET Framework データ型を受け入れる*p 入力してください*MFC は、この型の新しいオブジェクトをインスタンス化できるようにします。 *p 入力してください*必要があります、[型](/dotnet/api/system.type)データ型。

メソッドの 2 番目のオーバー ロードに基づき、Windows フォーム コントロールを作成し、`TManagedControl`のテンプレート パラメーター、`CWinFormsControl`クラス。 コントロールの位置とサイズがに基づいて、`RECT`メソッドに渡された構造体。 のみ*dwStyle*のスタイルには重要です。

メソッドの 3 番目のオーバー ロードは、破棄して、その位置、z オーダーとスタイルを仮定して、静的コントロールを置換する Windows フォーム コントロールを作成します。 スタティック コントロールは、Windows フォーム コントロールのプレース ホルダーとしてのみ機能します。 このオーバー ロードがからスタイルを結合、コントロールを作成するときに*dwStyle*静的コントロールのリソースのスタイルを使用します。

メソッドの 4 番目のオーバー ロードは、既にインスタンス化された Windows フォーム コントロールに渡すことができる*pControl* MFC をラップします。 同じ型でなければなりません、`TManagedControl`のテンプレート パラメーター、`CWinFormsControl`クラス。

参照してください[MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)サンプル [Windows フォームを使用して制御します。

##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl

MFC Windows フォーム コントロールのラッパー オブジェクトを構築します。

```
CWinFormsControl();
```

### <a name="remarks"></a>Remarks

呼び出すときに、Windows フォーム コントロールがインスタンス化[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)します。

##  <a name="getcontrol"></a>  CWinFormsControl::GetControl

Windows フォーム コントロールへのポインターを取得します。

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>戻り値

Windows フォーム コントロールへのポインターを返します。

### <a name="example"></a>例

  参照してください[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)します。

##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle

Windows フォーム コントロールを識別するハンドルを取得します。

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>戻り値

Windows フォーム コントロールにハンドルを返します。

### <a name="remarks"></a>Remarks

`GetControlHandle` .NET Framework のコントロール プロパティに格納されているウィンドウ ハンドルを返すヘルパー メソッド。 ウィンドウのハンドル値をコピー [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd)呼び出し中に[CWnd::Attach](../../mfc/reference/cwnd-class.md#attach)します。

##  <a name="operator_-_gt"></a>  CWinFormsControl::operator -&gt;

置換[CWinFormsControl::GetControl](#getcontrol)式で。

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>Remarks

この演算子は、置換する便利な構文を提供します。`GetControl`式で。

Windows フォームの詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。

##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl^

Windows フォーム コントロールへのポインターとして型をキャストします。

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>Remarks

この演算子は渡します`CWinFormsControl<TManagedControl>`Windows フォーム コントロールへのポインターをそのまま使用する関数。

## <a name="see-also"></a>関連項目

[CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)
