---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00ec945c5f0cdbb0c12f49b90719c31bf841ef2f
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121638"
---
# <a name="cwinformscontrol-class"></a>関数クラス
Windows フォーム コントロールのホスティング用の基本機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TManagedControl`  
 MFC アプリケーションに表示される .NET Framework の Windows フォーム コントロール。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows フォーム コントロールのラッパー オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|MFC コンテナーで Windows フォーム コントロールを作成します。|  
|[CWinFormsControl::GetControl](#getcontrol)|Windows フォーム コントロールへのポインターを取得します。|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows フォーム コントロールへのハンドルを取得します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|置換[CWinFormsControl::GetControl](#getcontrol)式でします。|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Windows フォーム コントロールへのポインターとして型をキャストします。|  
  
## <a name="remarks"></a>Remarks  
 `CWinFormsControl`クラスには、Windows フォーム コントロールのホスティングの基本的な機能が用意されています。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
 MFC コードは、ウィンドウ ハンドルをキャッシュする必要があります (通常に格納`m_hWnd`)。 一部の Windows フォーム コントロールのプロパティを必要とする、基になる Win32`Window`が破棄され、使用して再作成`DestroyWindow`と`CreateWindow`です。 MFC Windows フォームの実装のハンドル、`Destroy`と`Create`を更新するコントロールのイベント、`m_hWnd`メンバー。  
  
> [!NOTE]
>  MFC Windows フォームの統合は、(AFXDLL が定義されている) MFC と動的にリンクするプロジェクトでのみ動作します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl  
 MFC コンテナーで Windows フォーム コントロールを作成します。  
  
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
 *p 入力してください。*  
 作成するコントロールのデータ型。 必要があります、[型](https://msdn.microsoft.com/en-us/library/system.type)データ型。  
  
 *dwStyle*  
 コントロールに適用するウィンドウ スタイル。 組み合わせを指定[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。 現時点では、次のスタイルのみがサポートされている: WS_TABSTOP、WS_VISIBLE、WS_DISABLED および WS_GROUP です。  
  
 *rect*  
 A [RECT 構造体](../../mfc/reference/rect-structure1.md)コントロールの左上隅および右下隅の座標を定義する (最初のオーバー ロードだけ)。  
  
 *nPlaceHolderID*  
 静的なプレース ホルダー コントロールのハンドルでは、リソース エディターで配置されます。 新しく作成された Windows フォーム コントロールの位置、z オーダーとスタイルと仮定した場合、スタティック コントロールが置き換えられます (2 番目のオーバー ロードだけ)。  
  
 *pParentWnd*  
 親ウィンドウへのポインター。  
  
 *nID*  
 新しく作成されたコントロールに割り当てられるリソースの ID 番号。  
  
 *pControl*  
 関連付けられる Windows フォーム コントロールのインスタンス、[関数](../../mfc/reference/cwinformscontrol-class.md)(4 番目のオーバー ロードだけ) のオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、0 以外の値を返します。 失敗した場合は、0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、MFC コンテナー内の .NET Framework の Windows フォーム コントロールをインスタンス化します。  
  
 メソッドの最初のオーバー ロードは、.NET Framework データ型を受け入れる*p 入力してください*MFC は、この型の新しいオブジェクトをインスタンス化できるようにします。 *p 入力してください*する必要があります、[型](https://msdn.microsoft.com/en-us/library/system.type)データ型。  
  
 メソッドの 2 番目のオーバー ロードに基づく Windows フォーム コントロールを作成する、`TManagedControl`のテンプレート パラメーター、`CWinFormsControl`クラスです。 コントロールの位置とサイズがに基づいて、`RECT`構造が、メソッドに渡されます。 のみ*dwStyle*スタイルには重要です。  
  
 メソッドの 3 番目のオーバー ロードは、破棄して、その位置、z オーダーとスタイルを想定して、静的なコントロールを置換する Windows フォーム コントロールを作成します。 静的コントロールは、Windows フォーム コントロールのプレース ホルダーとしてのみ機能します。 このオーバー ロードがからスタイルを結合、コントロールを作成するときに*dwStyle*スタティック コントロールのリソースのスタイルを使用します。  
  
 メソッドの 4 番目のオーバー ロードは、既にインスタンス化された Windows フォーム コントロールに渡すことができる*pControl* MFC をラップします。 同じ型でなければなりません、`TManagedControl`のテンプレート パラメーター、`CWinFormsControl`クラスです。  
  
 参照してください[MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)サンプル Windows フォームを使用して制御します。  
  
##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl  
 MFC Windows フォーム コントロールのラッパー オブジェクトを構築します。  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出すときに、Windows フォーム コントロールがインスタンス化[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)です。  
  
##  <a name="getcontrol"></a>  CWinFormsControl::GetControl  
 Windows フォーム コントロールへのポインターを取得します。  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows フォーム コントロールへのポインターを返します。  
  
### <a name="example"></a>例  
  参照してください[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)です。  
  
##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle  
 Windows フォーム コントロールへのハンドルを取得します。  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows フォーム コントロールへのハンドルを返します。  
  
### <a name="remarks"></a>Remarks  
 `GetControlHandle` .NET Framework のコントロールのプロパティに格納されているウィンドウ ハンドルを返すヘルパー メソッドです。 ウィンドウのハンドル値をコピー [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd)への呼び出し中に[CWnd::Attach](../../mfc/reference/cwnd-class.md#attach)です。  
  
##  <a name="operator_-_gt"></a>  CWinFormsControl::operator-&gt;  
 置換[CWinFormsControl::GetControl](#getcontrol)式でします。  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Remarks  
 この演算子は、便利な構文を置き換える`GetControl`式でします。  
  
 Windows フォームの詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl ^  
 Windows フォーム コントロールへのポインターとして型をキャストします。  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Remarks  
 この演算子は渡します`CWinFormsControl<TManagedControl>`を Windows フォーム コントロールへのポインターを受け取る関数にします。  
  
## <a name="see-also"></a>関連項目  
 [CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)
