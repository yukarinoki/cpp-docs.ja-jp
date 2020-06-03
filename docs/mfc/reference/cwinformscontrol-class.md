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
ms.openlocfilehash: c91f50be1ea30efac81ff67c43633bedd7b0ca03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377174"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl クラス

Windows フォーム コントロールのホスティング用の基本機能を提供します。

## <a name="syntax"></a>構文

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>パラメーター

*コントロール制御*<br/>
MFC アプリケーションに表示される .NET Framework の Windows フォーム コントロール。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロール::CWin フォームコントロール](#cwinformscontrol)|MFC Windows フォーム コントロール ラッパー オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロールを作成します。](#createmanagedcontrol)|MFC コンテナーに Windows フォーム コントロールを作成します。|
|[コントロールを取得します。](#getcontrol)|Windows フォーム コントロールへのポインターを取得します。|
|[コントロールを取得します。](#getcontrolhandle)|Windows フォーム コントロールへのハンドルを取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コントロール: 演算子 -&gt;](#operator_-_gt)|式内の[CWinForms コントロール::GetControl](#getcontrol)を置き換えます。|
|[コントロール::演算子 TManagedControl^](#operator_tmanagedcontrol)|型を Windows フォーム コントロールへのポインターとしてキャストします。|

## <a name="remarks"></a>解説

この`CWinFormsControl`クラスは、Windows フォーム コントロールをホストするための基本的な機能を提供します。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

MFC コードは、ウィンドウ ハンドルをキャッシュしないようにする`m_hWnd`必要があります ( 通常は に格納されます)。 Windows フォーム コントロールのプロパティの中には、`Window`と を使用して`DestroyWindow`、基`CreateWindow`になる Win32 を破棄し、再作成する必要があるものがあります。 MFC Windows フォームの実装`Destroy`では`Create`、メンバーを更新するコントロールの`m_hWnd`イベントと イベントを処理します。

> [!NOTE]
> MFC Windows フォームの統合は、MFC (AFXDLL が定義されている) と動的にリンクするプロジェクトでのみ機能します。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h

## <a name="cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a>コントロールを作成します。

MFC コンテナーに Windows フォーム コントロールを作成します。

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

*pタイプ*<br/>
作成するコントロールのデータ型。 [型](/dotnet/api/system.type)データ型である必要があります。

*Dwstyle*<br/>
コントロールに適用するウィンドウ スタイル。 [[窓スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)]の組み合わせを指定します。 現在、WS_TABSTOP、WS_VISIBLE、WS_DISABLED、WS_GROUPのスタイルのみがサポートされています。

*Rect*<br/>
コントロールの左上隅と右下隅の座標を定義する[RECT 構造体](/windows/win32/api/windef/ns-windef-rect)です (最初のオーバーロードのみ)。

*スプレイスホルダーID*<br/>
リソース エディターに配置された静的なプレース ホルダー コントロールのハンドル。 新しく作成された Windows フォーム コントロールは、静的コントロールの位置、z オーダー、およびスタイルを想定して置き換えます (2 番目のオーバーロードのみ)。

*pParentWnd*<br/>
親ウィンドウへのポインター。

*nID*<br/>
新しく作成されたコントロールに割り当てられるリソース ID 番号。

*pControl*<br/>
[オブジェクト](../../mfc/reference/cwinformscontrol-class.md)に関連付ける Windows フォーム コントロールのインスタンスです (4 番目のオーバーロードのみ)。

### <a name="return-value"></a>戻り値

成功した場合は、0 以外の値を返します。 失敗した場合は、ゼロを返します。

### <a name="remarks"></a>解説

このメソッドは、MFC コンテナー内の .NET Framework Windows フォーム コントロールをインスタンス化します。

メソッドの最初のオーバーロードは、.NET Framework データ型*pType*を受け取り、MFC がこの型の新しいオブジェクトをインスタンス化できるようにします。 *pType は*[型](/dotnet/api/system.type)データ型である必要があります。

メソッドの 2 番目のオーバーロードは、クラスの`TManagedControl`テンプレート パラメーターに基づいて`CWinFormsControl`Windows フォーム コントロールを作成します。 コントロールのサイズと位置は、メソッドに渡される`RECT`構造体に基づいています。 スタイルの場合にのみ*dwStyle*が重要です。

メソッドの 3 番目のオーバーロードは、静的コントロールを破棄し、その位置、z オーダー、およびスタイルを想定して、Windows フォーム コントロールを作成します。 静的コントロールは、Windows フォーム コントロールのプレースホルダーとしてのみ機能します。 コントロールを作成するときに、このオーバーロードは *、dwStyle*のスタイルと静的コントロールのリソース スタイルを組み合わせます。

メソッドの 4 番目のオーバーロードでは、MFC がラップするインスタンス化済みの Windows フォーム*コントロール pControl*を渡すことができます。 クラスの`TManagedControl`テンプレート パラメーターと同じ型である`CWinFormsControl`必要があります。

[Windows フォーム コントロールの使用方法のサンプルについては、「MFC での](../../dotnet/using-a-windows-form-user-control-in-mfc.md)Windows フォーム ユーザー コントロールの使用」を参照してください。

## <a name="cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a>コントロール::CWin フォームコントロール

MFC Windows フォーム コントロール ラッパー オブジェクトを構築します。

```
CWinFormsControl();
```

### <a name="remarks"></a>解説

コントロールは、呼び出すとインスタンス化[されます](#createmanagedcontrol)。

## <a name="cwinformscontrolgetcontrol"></a><a name="getcontrol"></a>コントロールを取得します。

Windows フォーム コントロールへのポインターを取得します。

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>戻り値

Windows フォーム コントロールへのポインターを返します。

### <a name="example"></a>例

  「[コントロール::マネージ コントロールの作成](#createmanagedcontrol)」を参照してください。

## <a name="cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a>コントロールを取得します。

Windows フォーム コントロールへのハンドルを取得します。

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>戻り値

Windows フォーム コントロールへのハンドルを返します。

### <a name="remarks"></a>解説

`GetControlHandle`は、.NET Framework コントロールプロパティに格納されているウィンドウ ハンドルを返すヘルパー メソッドです。 ウィンドウ ハンドル値は[、CWnd::Attach](../../mfc/reference/cwnd-class.md#m_hwnd)の呼び出し中に[CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#attach)にコピーされます。

## <a name="cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a>コントロール: 演算子 -&gt;

式内の[CWinForms コントロール::GetControl](#getcontrol)を置き換えます。

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>解説

この演算子は、式内で置き`GetControl`換える便利な構文を提供します。

Windows フォームの詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a>コントロール::演算子 TManagedControl^

型を Windows フォーム コントロールへのポインターとしてキャストします。

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>解説

この演算子は、Windows`CWinFormsControl<TManagedControl>`フォーム コントロールへのポインターを受け取る関数に渡します。

## <a name="see-also"></a>関連項目

[CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)
