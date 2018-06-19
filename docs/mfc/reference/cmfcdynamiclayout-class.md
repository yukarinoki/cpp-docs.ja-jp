---
title: CMFCDynamicLayout クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
dev_langs:
- C++
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76faab221b5e36f9795595d07cd13d0bbf1df200
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370722"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout クラス
ユーザーによるウィンドウ サイズの変更時に、ウィンドウのコントロールをどのように移動して、サイズを変更するかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|`CMFCDynamicLayout` オブジェクトを構築します。|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cmfcdynamiclayout::additem](#additem)|子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。|  
|[Cmfcdynamiclayout::adjust](#adjust)|子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。|  
|[CMFCDynamicLayout::Create](#create)|ホスト ウィンドウを格納し、検証します。|  
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|ホスト ウィンドウへのポインターを返します。|  
|[CMFCDynamicLayout::GetMinSize](#getminsize)|レイアウト調整の下限のウィンドウ サイズを返します。|  
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|ウィンドウの現在のクライアント領域の長方形を取得します。|  
|[Cmfcdynamiclayout::hasitem](#hasitem)|子コントロールが動的レイアウトに追加されたかどうかを確認します。|  
|[Cmfcdynamiclayout::isempty](#isempty)|動的なレイアウトに子ウィンドウが追加されていないことを確認します。|  
|[CMFCDynamicLayout::LoadResource](#loadresource)|AFX_DIALOG_LAYOUT リソースから動的レイアウトを読み取り、ホスト ウィンドウにそのレイアウトを適用します。|  
|静的[CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|取得、 [MoveSettings](#movesettings_structure)とき、ユーザーがそのホスト ウィンドウで、どの程度の子コントロールを水平方向に移動を定義する値。|  
|静的[CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|取得、 [MoveSettings](#movesettings_structure)とき、ユーザーがそのホスト ウィンドウで、どの程度の子コントロールを水平方向に移動を定義する値。|  
|静的[CMFCDynamicLayout::MoveNone](#movenone)|取得、 [MoveSettings](#movesettings_structure)なしを表す垂直または水平方向の子コントロールの値。|  
|静的[CMFCDynamicLayout::MoveVertical](#movevertical)|取得、 [MoveSettings](#movesettings_structure)とき、ユーザーがそのホスト ウィンドウで、どの程度の子コントロールを垂直方向に移動を定義する値。|  
|[CMFCDynamicLayout::SetMinSize](#setminsize)|ウィンドウ サイズをレイアウト調整の下限に設定します。|  
|静的[CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|取得、 [SizeSettings](#sizesettings_structure)ユーザーがホストしているウィンドウをサイズ変更時に、どの程度子コントロールが水平方向にサイズを定義する値。|  
|静的[CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|取得、 [SizeSettings](#sizesettings_structure)ユーザーがホストしているウィンドウをサイズ変更時に、どの程度子コントロールが水平方向にサイズを定義する値。|  
|静的[CMFCDynamicLayout::SizeNone](#sizenone)|取得、 [SizeSettings](#sizesettings_structure)値なしを表す子コントロールのサイズ変更します。|  
|静的[CMFCDynamicLayout::SizeVertical](#sizevertical)|取得、 [SizeSettings](#sizesettings_structure)ユーザーがホストしているウィンドウをサイズ変更時に、どの程度子コントロールが垂直方向にサイズを定義する値。|  
  
## <a name="nested-types"></a>入れ子にされた型  
  
|名前|説明|  
|----------|-----------------|  
|[Cmfcdynamiclayout::movesettings 構造体](#movesettings_structure)|動的レイアウトでのコントロールの移動データをカプセル化します。|  
|[Cmfcdynamiclayout::sizesettings 構造体](#sizesettings_structure)|動的レイアウトでのコントロールのサイズ変更データをカプセル化します。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxlayout.h  
  
##  <a name="additem"></a>  Cmfcdynamiclayout::additem  
 子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。  
  
```  
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

 
BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```  
  
### <a name="parameters"></a>パラメーター  
 `hwnd`  
 追加するウィンドウへのハンドル。  
  
 `nID`  
 追加する子コントロールの ID。  
  
 `moveSettings`  
 ウィンドウ サイズの変更に合わせてコントロールを移動する方法を記述する構造体。  
  
 `sizeSettings`  
 ウィンドウ サイズの変更に合わせてコントロールのサイズを変更する方法を記述する構造体。  
  
### <a name="return-value"></a>戻り値  
 項目が正常に追加された場合は true。それ以外の場合は false。  
  
### <a name="remarks"></a>コメント  
 ホスティング ウィンドウのサイズを変更するとき、子コントロールの位置とサイズが動的に変更されます。  
  
##  <a name="adjust"></a>  Cmfcdynamiclayout::adjust  
 子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。  
  
```  
void Adjust();
```  
  
### <a name="remarks"></a>コメント  
 ホスティング ウィンドウのサイズを変更するとき、子コントロールの位置とサイズが動的に変更されます。  
  
##  <a name="create"></a>  CMFCDynamicLayout::Create  
 ホスト ウィンドウを格納し、検証します。  
  
```  
BOOL Create(CWnd* pHostWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 pHostWnd  
 ホスト ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 作成が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gethostwnd"></a>  CMFCDynamicLayout::GetHostWnd  
 ホスト ウィンドウへのポインターを返します。  
  
```  
CWnd* GetHostWnd();
```  
  
### <a name="return-value"></a>戻り値  
 ホスト ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定では、すべての子コントロールの位置はこのウィンドウに合わせて再計算されます。  
  
##  <a name="getminsize"></a>  CMFCDynamicLayout::GetMinSize  
 レイアウト調整の下限のウィンドウ サイズを返します。  
  
```  
CSize GetMinSize();
```  
  
### <a name="return-value"></a>戻り値  
 レイアウト調整の下限のウィンドウ サイズ。  
  
### <a name="remarks"></a>コメント  
 ホスティング ウィンドウのサイズ変更が行われると、子コントロールの位置とサイズが動的に変更されます。ただし、コントロールは最小サイズが決まっており、これを下回った場合にはレイアウトが調整されません。 ウィンドウ サイズをこの最小サイズよりも小さくすることは可能ですが、その場合、ウィンドウの一部がビューに表示されなくなります。  
  
##  <a name="getwindowrect"></a>  CMFCDynamicLayout::GetWindowRect  
 ウィンドウの現在のクライアント領域の長方形を取得します。  
  
```  
void GetHostWndRect(CRect& rect,);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 関数から制御が戻った後、このパラメーターにはレイアウト領域に外接する四角形が含まれています。 これは out パラメーターです。入力値は上書きされます。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasitem"></a>  Cmfcdynamiclayout::hasitem  
 子コントロールが動的レイアウトに追加されたかどうかを確認します。  
  
```  
BOOL HasItem(HWND hwnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hwnd`  
 コントロールのウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 この項目がレイアウトに既に存在する場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isempty"></a>  Cmfcdynamiclayout::isempty  
 動的なレイアウトに子ウィンドウが追加されていないことを確認します。  
  
```  
BOOL IsEmpty();
```  
  
### <a name="return-value"></a>戻り値  
 レイアウトに項目がない場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="loadresource"></a>  CMFCDynamicLayout::LoadResource  
 AFX_DIALOG_LAYOUT リソースから動的レイアウトを読み取り、ホスト ウィンドウにそのレイアウトを適用します。  
  
```  
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pHostWnd`  
 ホスト ウィンドウへのポインター。  
  
 `lpResource`  
 AFX_DIALOG_LAYOUT リソースが含まれるバッファーへのポインター。  
  
 `dwSize`  
 バイト単位のバッファー サイズ。  
  
### <a name="return-value"></a>戻り値  
 リソースが読み込まれ、ホスト ウィンドウに適用される場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="movehorizontal"></a>  CMFCDynamicLayout::MoveHorizontal  
 取得、 [MoveSettings](#movesettings_structure)とき、ユーザーがそのホスト ウィンドウで、どの程度の子コントロールを水平方向に移動を定義する値。  
  
```  
static MoveSettings MoveHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを水平方向に移動する量をパーセンテージとして定義します。  
  
### <a name="return-value"></a>戻り値  
 A [MoveSettings](#movesettings_structure)移動比率をカプセル化、要求された値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="movehorizontalandvertical"></a>  CMFCDynamicLayout::MoveHorizontalAndVertical  
 取得、 [MoveSettings](#movesettings_structure)とき、ユーザーがそのホスト ウィンドウで、どの程度の子コントロールを水平方向に移動を定義する値。  
  
```  
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nXRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを水平方向に移動する量をパーセンテージとして定義します。  
  
 `nYRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを垂直方向に移動する量をパーセンテージとして定義します。  
  
### <a name="return-value"></a>戻り値  
 A [MoveSettings](#movesettings_structure)移動比率をカプセル化、要求された値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="movenone"></a>  CMFCDynamicLayout::MoveNone  
 取得、 [MoveSettings](#movesettings_structure)なしを表す垂直または水平方向の子コントロールの値。  
  
```  
static MoveSettings MoveNone();  
```  
  
### <a name="return-value"></a>戻り値  
 A [MoveSettings](#movesettings_structure)ように、ユーザーがホスト ウィンドウは移動しませんできるように、代わりに、コントロールを修正する値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="movesettings_structure"></a>  Cmfcdynamiclayout::movesettings 構造体  
 動的レイアウトでのコントロールの移動データをカプセル化します。  
  
```  
struct CMFCDynamicLayout::MoveSettings;  
```  
  
### <a name="remarks"></a>コメント  
 これは、`CMFCDynamicLayout` 内の入れ子にされたクラスです。  

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal
データの移動が 0 以外の水平方向の移動を指定しているかどうかを確認します。  
  

```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>戻り値  
 `MoveSettings` オブジェクトが 0 以外の水平方向の移動を指定している場合は TRUE です。  

 ## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone
 移動データが移動なしを指定しているかどうかを確認します。  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>戻り値  
 `MoveSettings` オブジェクトが移動なしを指定している場合は TRUE です。  

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical
  データの移動が 0 以外の垂直方向の移動を指定しているかどうかを確認します。  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>戻り値  
 `MoveSettings` オブジェクトが 0 以外の垂直方向の移動を指定している場合は TRUE です。  

##  <a name="movevertical"></a>  CMFCDynamicLayout::MoveVertical  
 取得、 [MoveSettings](#movesettings_structure)とき、ユーザーがそのホスト ウィンドウで、どの程度の子コントロールを垂直方向に移動を定義する値。  
  
```  
static MoveSettings MoveVertical(int nRatio);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを垂直方向に移動する量をパーセンテージとして定義します。  
  
### <a name="return-value"></a>戻り値  
 A [MoveSettings](#movesettings_structure)移動比率をカプセル化、要求された値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setminsize"></a>  CMFCDynamicLayout::SetMinSize  
 ウィンドウ サイズをレイアウト調整の下限に設定します。  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 レイアウト調整が可能な最小サイズ。  
  
### <a name="remarks"></a>コメント  
 ホスティング ウィンドウのサイズ変更が行われると、子コントロールの位置とサイズが動的に変更されます。ただし、コントロールは最小サイズが決まっており、これを下回った場合にはレイアウトが調整されません。 ウィンドウ サイズをこの最小サイズよりも小さくすることは可能ですが、その場合、ウィンドウの一部がビューに表示されなくなります。  
  
##  <a name="sizehorizontal"></a>  CMFCDynamicLayout::SizeHorizontal  
 取得、 [SizeSettings](#sizesettings_structure)ユーザーがホストしているウィンドウをサイズ変更時に、どの程度子コントロールが水平方向にサイズを定義する値。  
  
```  
static SizeSettings SizeHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの水平方向のサイズを変更する量をパーセンテージとして定義します。  
  
### <a name="return-value"></a>戻り値  
 A [SizeSettings](#sizesettings_structure)要求されたサイズ比率をカプセル化する値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sizehorizontalandvertical"></a>  CMFCDynamicLayout::SizeHorizontalAndVertical  
 取得、 [SizeSettings](#sizesettings_structure)ユーザーがホストしているウィンドウをサイズ変更時に、どの程度子コントロールが水平方向にサイズを定義する値。  
  
```  
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nXRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの水平方向のサイズを変更する量をパーセンテージとして定義します。  
  
 `nYRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの垂直方向のサイズを変更する量をパーセンテージとして定義します。  
  
### <a name="return-value"></a>戻り値  
 A [SizeSettings](#sizesettings_structure)要求されたサイズ比率をカプセル化する値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sizenone"></a>  CMFCDynamicLayout::SizeNone  
 取得、 [SizeSettings](#sizesettings_structure)値なしを表す子コントロールのサイズ変更します。  
  
```  
static SizeSettings SizeNone();  
```  
  
### <a name="return-value"></a>戻り値  
 A [SizeSettings](#sizesettings_structure)ように、ユーザーがホスト ウィンドウ、サイズは変更しないように、特定のサイズでコントロールを修正する値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sizesettings_structure"></a>  Cmfcdynamiclayout::sizesettings 構造体  
 動的レイアウトでのコントロールのサイズ変更データをカプセル化します。  
  
```  
struct CMFCDynamicLayout::SizeSettings;  
```  
  
### <a name="remarks"></a>コメント  
 これは、`CMFCDynamicLayout` 内の入れ子にされたクラスです。  

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal
サイズ変更データが、0 以外の水平方向のサイズ変更枠を指定しているかどうかを確認します。  
  
```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>戻り値  
 `SizeSettings` オブジェクトが、0 以外の水平方向のサイズ変更枠を指定している場合は TRUE です。 

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone
サイズ変更データが、サイズ変更枠を指定していないかどうかを確認します。  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>戻り値  
 `SizeSettings` オブジェクトがサイズ変更枠を指定しない場合は TRUE です。  

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical
サイズ変更データが、0 以外の垂直方向のサイズ変更枠を指定しているかどうかを確認します。  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>戻り値  
 `SizeSettings` オブジェクトが、0 以外の垂直方向のサイズ変更枠を指定している場合は TRUE です。  

##  <a name="sizevertical"></a>  CMFCDynamicLayout::SizeVertical  
 取得、 [SizeSettings](#sizesettings_structure)ユーザーがホストしているウィンドウをサイズ変更時に、どの程度子コントロールが垂直方向にサイズを定義する値。  
  
```  
static SizeSettings SizeVertical(int nRatio);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nRatio`  
 ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの垂直方向のサイズを変更する量をパーセンテージとして定義します。  
  
### <a name="return-value"></a>戻り値  
 A [SizeSettings](#sizesettings_structure)要求されたサイズ比率をカプセル化する値。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
