---
description: '詳細情報: CWinFormsControl クラス'
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
ms.openlocfilehash: 32daf5f1bf9efcd5d5b17d134dc8deaee7e32527
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318443"
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
MFC アプリケーションに表示される .NET Framework Windows フォームコントロール。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows フォームコントロールラッパーオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|MFC コンテナーに Windows フォームコントロールを作成します。|
|[CWinFormsControl:: GetControl](#getcontrol)|Windows フォームコントロールへのポインターを取得します。|
|[CWinFormsControl:: GetControlHandle](#getcontrolhandle)|Windows フォームコントロールへのハンドルを取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CWinFormsControl:: operator-&gt;](#operator_-_gt)|式の [CWinFormsControl:: GetControl](#getcontrol) を置き換えます。|
|[CWinFormsControl:: operator TManagedControl ^](#operator_tmanagedcontrol)|型を Windows フォームコントロールへのポインターとしてキャストします。|

## <a name="remarks"></a>解説

クラスは、 `CWinFormsControl` Windows フォームコントロールをホストするための基本機能を提供します。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

MFC コードでは、ウィンドウハンドル (通常はに格納されている) をキャッシュしないでください `m_hWnd` 。 一部の Windows フォームコントロールプロパティでは、とを使用して、基になる Win32 を `Window` 破棄して再作成する必要があり `DestroyWindow` `CreateWindow` ます。 MFC Windows フォームの実装では `Destroy` 、 `Create` メンバーを更新するコントロールのイベントとイベントを処理し `m_hWnd` ます。

> [!NOTE]
> MFC Windows フォーム統合は、MFC と動的にリンクするプロジェクト (AFXDLL が定義されているプロジェクト) でのみ機能します。

## <a name="requirements"></a>要件

**ヘッダー:** afxwinforms

## <a name="cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a> CWinFormsControl::CreateManagedControl

MFC コンテナーに Windows フォームコントロールを作成します。

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
作成するコントロールのデータ型。 [型](/dotnet/api/system.type)のデータ型である必要があります。

*dwStyle*<br/>
コントロールに適用するウィンドウスタイル。 [ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)の組み合わせを指定します。 現時点では、WS_TABSTOP、WS_VISIBLE、WS_DISABLED、および WS_GROUP のスタイルのみがサポートされています。

*rect*<br/>
コントロールの左上隅と右下隅の座標を定義する [RECT 構造体](/windows/win32/api/windef/ns-windef-rect) (最初のオーバーロードのみ)。

*nPlaceHolderID*<br/>
リソースエディターに配置された静的プレースホルダーコントロールのハンドル。 新しく作成された Windows フォームコントロールは、その位置、z オーダー、およびスタイル (2 番目のオーバーロードのみ) を想定して、静的コントロールを置き換えます。

*pParentWnd*<br/>
親ウィンドウへのポインター。

*nID*<br/>
新しく作成されたコントロールに割り当てられるリソース ID 番号。

*pControl*<br/>
[CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md)オブジェクトに関連付ける Windows フォームコントロールのインスタンス (4 番目のオーバーロードのみ)。

### <a name="return-value"></a>戻り値

成功した場合、は0以外の値を返します。 失敗した場合は、0を返します。

### <a name="remarks"></a>解説

このメソッドは、MFC コンテナー内の .NET Framework Windows フォームコントロールをインスタンス化します。

メソッドの最初のオーバーロードでは、MFC がこの型の新しいオブジェクトをインスタンス化できるように、.NET Framework データ型 *pType* を受け取ります。 *pType* は [型](/dotnet/api/system.type) のデータ型である必要があります。

メソッドの2番目のオーバーロードは、クラスのテンプレートパラメーターに基づいて Windows フォームコントロールを作成し `TManagedControl` `CWinFormsControl` ます。 コントロールのサイズと位置は、 `RECT` メソッドに渡される構造体に基づいています。 スタイルには *dwStyle* のみが重要です。

メソッドの3番目のオーバーロードは、静的コントロールを置き換える Windows フォームコントロールを作成し、そのコントロールを破棄して、位置、z オーダー、およびスタイルを想定します。 スタティックコントロールは、Windows フォームコントロールのプレースホルダーとしてのみ機能します。 このオーバーロードは、コントロールを作成するときに、 *dwStyle* のスタイルと静的コントロールのリソーススタイルを結合します。

メソッドの4番目のオーバーロードを使用すると、既にインスタンス化されている Windows フォームコントロールの *Pcontrol* コントロールを渡すことができます。 これは、クラスのテンプレートパラメーターと同じ型である必要があり `TManagedControl` `CWinFormsControl` ます。

Windows フォームコントロールの使用に関するサンプルについては [、「MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 」を参照してください。

## <a name="cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a> CWinFormsControl::CWinFormsControl

MFC Windows フォームコントロールラッパーオブジェクトを構築します。

```
CWinFormsControl();
```

### <a name="remarks"></a>解説

[CWinFormsControl:: CreateManagedControl](#createmanagedcontrol)を呼び出すと、Windows フォームコントロールがインスタンス化されます。

## <a name="cwinformscontrolgetcontrol"></a><a name="getcontrol"></a> CWinFormsControl:: GetControl

Windows フォームコントロールへのポインターを取得します。

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>戻り値

Windows フォームコントロールへのポインターを返します。

### <a name="example"></a>例

  「 [CWinFormsControl:: CreateManagedControl](#createmanagedcontrol)」を参照してください。

## <a name="cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a> CWinFormsControl:: GetControlHandle

Windows フォームコントロールへのハンドルを取得します。

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>戻り値

Windows フォームコントロールへのハンドルを返します。

### <a name="remarks"></a>解説

`GetControlHandle` は、.NET Framework コントロールのプロパティに格納されているウィンドウハンドルを返すヘルパーメソッドです。 [Cwnd:: Attach](../../mfc/reference/cwnd-class.md#attach)の呼び出し中に、ウィンドウハンドルの値が[cwnd:: m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd)にコピーされます。

## <a name="cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a> CWinFormsControl:: operator-&gt;

式の [CWinFormsControl:: GetControl](#getcontrol) を置き換えます。

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>解説

この演算子は、式で置き換えられる便利な構文を提供 `GetControl` します。

Windows フォームの詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a> CWinFormsControl:: operator TManagedControl ^

型を Windows フォームコントロールへのポインターとしてキャストします。

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>解説

この演算子は `CWinFormsControl<TManagedControl>` 、Windows フォームコントロールへのポインターを受け取る関数に渡します。

## <a name="see-also"></a>関連項目

[CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)
