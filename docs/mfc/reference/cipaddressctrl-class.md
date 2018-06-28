---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
dev_langs:
- C++
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3e5f88dc011e358c0438209f0a4b3e277419be9
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042158"
---
# <a name="cipaddressctrl-class"></a>関数クラス
Windows コモン IP アドレス コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|`CIPAddressCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|IP アドレス コントロールの内容を消去します。|  
|[CIPAddressCtrl::Create](#create)|IP アドレス コントロールを作成し、それにアタッチ、`CIPAddressCtrl`オブジェクト。|  
|[CIPAddressCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用して、IP アドレス コントロールを作成しにアタッチ、`CIPAddressCtrl`オブジェクト。|  
|[CIPAddressCtrl::GetAddress](#getaddress)|IP アドレス コントロール内のすべての 4 つのフィールドのアドレス値を取得します。|  
|[CIPAddressCtrl::IsBlank](#isblank)|IP アドレス コントロールのすべてのフィールドが空かを判断します。|  
|[CIPAddressCtrl::SetAddress](#setaddress)|IP アドレス コントロールの 4 つすべてのフィールドのアドレス値を設定します。|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|IP アドレス コントロールの指定したフィールドにキーボード フォーカスを設定します。|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|IP アドレス コントロール内の指定したフィールドに範囲を設定します。|  
  
## <a name="remarks"></a>Remarks  
 IP アドレスのコントロールのエディット コントロールのようなコントロールを使用すると、入力およびインターネット プロトコル (IP) 形式で数値のアドレスを操作できます。  
  
 このコントロール (および、`CIPAddressCtrl`クラス) は、Microsoft Internet Explorer 4.0 以降を実行中のプログラムにのみ使用できます。 また、将来のバージョンの Windows および Windows NT で使用可能なにもなります。  
  
 IP アドレス コントロールの概要については、次を参照してください。 [IP アドレス コントロール](http://msdn.microsoft.com/library/windows/desktop/bb761372)Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="cipaddressctrl"></a>  CIPAddressCtrl::CIPAddressCtrl  
 
          `CIPAddressCtrl` オブジェクトを作成します。  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="clearaddress"></a>  CIPAddressCtrl::ClearAddress  
 IP アドレス コントロールの内容を消去します。  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377)Windows SDK で説明されている。  
  
##  <a name="create"></a>  CIPAddressCtrl::Create  
 IP アドレス コントロールを作成し、それにアタッチ、`CIPAddressCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 IP アドレス コントロールのスタイルです。 ウィンドウ スタイルの組み合わせを適用します。 含める必要があります、 **WS_CHILD**スタイルのコントロールが子ウィンドウにある必要があります。 参照してください[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)ウィンドウ スタイルの一覧については Windows SDK に含まれています。  
  
 *rect*  
 IP アドレス コントロールのサイズと位置への参照。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 *pParentWnd*  
 IP アドレス コントロールの親ウィンドウへのポインター。 なければなりません**NULL です。**  
  
 *nID*  
 IP アドレス コントロールの id。  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CIPAddressCtrl` 2 つのステップ内のオブジェクト。  
  
1.  作成するコンス トラクターを呼び出して、`CIPAddressCtrl`オブジェクト。  
  
2.  呼び出す`Create`、IP アドレス コントロールを作成します。  
  
 拡張ウィンドウ スタイルをコントロールに使用する場合は、呼び出す[CreateEx](#createex)の代わりに`Create`です。  
  
##  <a name="createex"></a>  CIPAddressCtrl::CreateEx  
 コントロールを作成し、(子ウィンドウ) でそれを関連付けるには、この関数を呼び出して、`CIPAddressCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwExStyle*  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 *dwStyle*  
 IP アドレス コントロールのスタイルです。 ウィンドウ スタイルの組み合わせを適用します。 含める必要があります、 **WS_CHILD**スタイルのコントロールが子ウィンドウにある必要があります。 参照してください[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)ウィンドウ スタイルの一覧については Windows SDK に含まれています。  
  
 *rect*  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体*pParentWnd*です。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress  
 IP アドレス コントロール内のすべての 4 つのフィールドのアドレス値を取得します。  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>パラメーター  
 *nField0*  
 パックされた IP アドレスからフィールド 0 の値への参照。  
  
 *nField1*  
 パックされた IP アドレスからフィールド 1 の値への参照。  
  
 *nField2*  
 パックされた IP アドレスからフィールド 2 の値への参照。  
  
 *nField3*  
 パックされた IP アドレスからフィールド 3 の値への参照。  
  
 *dwAddress*  
 アドレスへの参照、 `DWORD` IP アドレスを受信する値。 参照してください**解説**を示すテーブルを方法*dwAddress*入力されます。  
  
### <a name="return-value"></a>戻り値  
 IP アドレス コントロール内の空白でないフィールドの数。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378)Windows SDK で説明されている。 最初のプロトタイプでは、番号は、0 ~ 3 で、コントロールのフィールドを読み取るそれぞれ左から右、4 つのパラメーターを設定します。 上記の 2 番目のプロトタイプで*dwAddress*は次のように設定されます。  
  
|フィールド|ビット フィールドの値を含む|  
|-----------|-------------------------------------|  
|0|24 31 ~|  
|1|16 ~ 23|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank  
 IP アドレス コントロールのすべてのフィールドが空かを判断します。  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>戻り値  
 すべての IP アドレス コントロールのフィールドは空以外の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379)Windows SDK で説明されている。  
  
##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress  
 IP アドレス コントロールの 4 つすべてのフィールドのアドレス値を設定します。  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>パラメーター  
 *nField0*  
 パックされた IP アドレスからフィールド 0 の値。  
  
 *nField1*  
 パックされた IP アドレスから 1 フィールドの値。  
  
 *nField2*  
 パックされた IP アドレスから 2 フィールドの値。  
  
 *nField3*  
 パックされた IP アドレスからフィールド 3 の値。  
  
 *dwAddress*  
 A`DWORD`新しい IP アドレスを含む値です。 参照してください**解説**を示す表の方法、`DWORD`値を指定します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380)Windows SDK で説明されている。 最初のプロトタイプでは、番号は、0 ~ 3 で、コントロールのフィールドを読み取るそれぞれ左から右、4 つのパラメーターを設定します。 上記の 2 番目のプロトタイプで*dwAddress*は次のように設定されます。  
  
|フィールド|ビット フィールドの値を含む|  
|-----------|-------------------------------------|  
|0|24 31 ~|  
|1|16 ~ 23|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus  
 IP アドレス コントロールの指定したフィールドにキーボード フォーカスを設定します。  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>パラメーター  
 *nField*  
 フィールドの 0 から始まるインデックスがフォーカスを設定する必要があります。 この値がフィールドの数よりも大きい場合、フォーカスは最初の空白のフィールドに設定されます。 すべてのフィールドが空白以外の場合は、フォーカスは最初のフィールドに設定されます。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381)Windows SDK で説明されている。  
  
##  <a name="setfieldrange"></a>  CIPAddressCtrl::SetFieldRange  
 IP アドレス コントロール内の指定したフィールドに範囲を設定します。  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>パラメーター  
 *nField*  
 範囲の適用先となるフィールドを 0 から始まるインデックス。  
  
 *上限値*  
 この IP アドレス コントロールの指定したフィールドの下限値を受け取る整数への参照。  
  
 *下限*  
 この IP アドレス コントロールの指定したフィールドの数の上限を受け取る整数への参照。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382)Windows SDK で説明されている。 2 つのパラメーターを使用して*上限値*と*下限*の代わりに、フィールドの下限と上限の制限を示すために、 *wRange* Win32 メッセージで使用されるパラメーター。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



