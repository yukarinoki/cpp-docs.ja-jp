---
title: CIPAddressCtrl クラス |Microsoft Docs
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
ms.openlocfilehash: b6c7d45c36534ab2c67765dc6e4e9ea61b79b3ea
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338033"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl クラス
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
|[CIPAddressCtrl::Create](#create)|IP アドレス コントロールを作成しにアタッチします、`CIPAddressCtrl`オブジェクト。|  
|[CIPAddressCtrl::CreateEx](#createex)|指定した Windows の拡張スタイルを使用して、IP アドレス コントロールを作成しにアタッチします、`CIPAddressCtrl`オブジェクト。|  
|[CIPAddressCtrl::GetAddress](#getaddress)|4 つすべての IP アドレスのコントロール フィールドのアドレス値を取得します。|  
|[CIPAddressCtrl::IsBlank](#isblank)|IP アドレス コントロールのすべてのフィールドが空かを判断します。|  
|[CIPAddressCtrl::SetAddress](#setaddress)|IP アドレス コントロールの 4 つすべてのフィールドのアドレス値を設定します。|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|IP アドレスのコントロールで指定されたフィールドにキーボード フォーカスを設定します。|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|IP アドレス コントロール内の指定したフィールドに範囲を設定します。|  
  
## <a name="remarks"></a>Remarks  
 IP アドレスのコントロールのエディット コントロールのようなコントロールを入力し、インターネット プロトコル (IP) の形式で数値のアドレスを操作することができます。  
  
 このコントロール (つまり、`CIPAddressCtrl`クラス) は Microsoft Internet Explorer 4.0 以降を実行中のプログラムでのみ使用できます。 Windows および Windows NT の将来のバージョンで使用可能なもされます。  
  
 IP アドレスの管理の概要については、次を参照してください。 [IP アドレス コントロール](http://msdn.microsoft.com/library/windows/desktop/bb761372)Windows SDK に含まれています。  
  
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
 このメンバー関数は、Win32 メッセージの動作を実装[IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377)」の説明に従って、Windows SDK。  
  
##  <a name="create"></a>  CIPAddressCtrl::Create  
 IP アドレス コントロールを作成しにアタッチします、`CIPAddressCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 IP アドレス コントロールのスタイル。 ウィンドウ スタイルの組み合わせを適用します。 コントロールが子ウィンドウにある必要がありますので、WS_CHILD スタイルを含める必要があります。 参照してください[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) windows スタイルの一覧については、Windows SDK に含まれています。  
  
 *rect*  
 IP アドレス コントロールのサイズと位置への参照。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 *pParentWnd*  
 IP アドレス コントロールの親ウィンドウへのポインター。 NULL は指定できません。  
  
 *nID*  
 IP アドレス コントロールの id。  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CIPAddressCtrl` 2 つのステップ内のオブジェクト。  
  
1.  作成するコンス トラクターを呼び出す、`CIPAddressCtrl`オブジェクト。  
  
2.  呼び出す`Create`、IP アドレスのコントロールを作成します。  
  
 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに`Create`します。  
  
##  <a name="createex"></a>  CIPAddressCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CIPAddressCtrl`オブジェクト。  
  
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
 作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK に含まれています。  
  
 *dwStyle*  
 IP アドレス コントロールのスタイル。 ウィンドウ スタイルの組み合わせを適用します。 コントロールが子ウィンドウにある必要がありますので、WS_CHILD スタイルを含める必要があります。 参照してください[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) windows スタイルの一覧については、Windows SDK に含まれています。  
  
 *rect*  
 参照を[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用`CreateEx`の代わりに[作成](#create)、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress  
 4 つすべての IP アドレスのコントロール フィールドのアドレス値を取得します。  
  
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
 IP アドレスを受け取る DWORD 値のアドレスへの参照。 参照してください**解説**を示すテーブルをどのように*dwAddress*が入力されます。  
  
### <a name="return-value"></a>戻り値  
 IP アドレス コントロール内の空白でないフィールドの数。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378)」の説明に従って、Windows SDK。 最初のプロトタイプで読み取るフィールド 0 ~ コントロールの 3 内の数値の左から右それぞれ、4 つのパラメーターを設定します。 上記の 2 つ目のプロトタイプで*dwAddress*は次のように設定されます。  
  
|フィールド|ビット フィールドの値を格納しています。|  
|-----------|-------------------------------------|  
|0|24 ~ 31|  
|1|16 ~ 23|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank  
 IP アドレス コントロールのすべてのフィールドが空かを判断します。  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>戻り値  
 すべての IP アドレス コントロール フィールドが空以外の場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379)」の説明に従って、Windows SDK。  
  
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
 フィールド 0 の値は、パックされた IP アドレス。  
  
 *nField1*  
 パックされた IP アドレスから 1 フィールドの値。  
  
 *nField2*  
 パックされた IP アドレスから 2 フィールドの値。  
  
 *nField3*  
 パックされた IP アドレスから 3 のフィールドの値。  
  
 *dwAddress*  
 新しい IP アドレスを含む DWORD 値を指定します。 参照してください**解説**の表に、DWORD 値を格納する方法を示します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380)」の説明に従って、Windows SDK。 最初のプロトタイプで読み取るフィールド 0 ~ コントロールの 3 内の数値の左から右それぞれ、4 つのパラメーターを設定します。 上記の 2 つ目のプロトタイプで*dwAddress*は次のように設定されます。  
  
|フィールド|ビット フィールドの値を格納しています。|  
|-----------|-------------------------------------|  
|0|24 ~ 31|  
|1|16 ~ 23|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus  
 IP アドレスのコントロールで指定されたフィールドにキーボード フォーカスを設定します。  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>パラメーター  
 *nField*  
 0 から始まるフィールド インデックスがフォーカスを設定する必要があります。 この値がフィールドの数より大きい場合は、最初の空フィールドにフォーカスが設定されます。 すべてのフィールドが空白以外の場合は、最初のフィールドにフォーカスが設定されます。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381)」の説明に従って、Windows SDK。  
  
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
 範囲の適用先となる 0 から始まるフィールド インデックス。  
  
 *上限値*  
 この IP アドレス コントロールで指定されたフィールドの下限値を受け取る整数への参照。  
  
 *下限*  
 この IP アドレス コントロールで指定されたフィールドの上限値を受け取る整数への参照。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382)」の説明に従って、Windows SDK。 2 つのパラメーターを使用して、*上限値*と*下限*の代わりに、フィールドの上限と下限の制限を示すために、 *wRange* Win32 メッセージで使用されるパラメーター。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



