---
title: CMFCMaskedEdit クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
dev_langs:
- C++
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 985cd4011dbb1ea8ccad7cd40c81833dd5507f11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit クラス
`CMFCMaskedEdit`クラスは、ユーザー入力をマスクを検証し、テンプレートに従って検証結果を表示するマスク エディット コントロールをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|既定のコンストラクター|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|ユーザー入力の検証を無効にします。|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|指定するかどうか、`GetWindowText`メソッドは、マスクされた文字のみを取得します。|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|編集コントロールのマスクを初期化します。|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|マスク エディット コントロールがユーザー入力、またはすべてのユーザー入力の特定のグループを選択するかどうかを指定します。|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|マスク全体またはテキストを検証しているだけで、文字をマスクするかどうかを指定します。|  
|`CMFCMaskedEdit::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|検証済みのマスク エディット コントロールからテキストを取得します。|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|ユーザーが入力できる有効な文字の文字列を指定します。|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|マスク エディット コントロールで、プロンプトを表示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|対応するマスク文字に対して指定した文字を検証するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 使用する次の手順を実行、`CMFCMaskedEdit`アプリケーションで制御します。  
  
 1. 埋め込み、`CMFCMaskedEdit`ウィンドウ クラスのオブジェクト。  
  
 2. 呼び出す、 [CMFCMaskedEdit::EnableMask](#enablemask)マスクを指定します。  
  
 3. 呼び出す、 [CMFCMaskedEdit::SetValidChars](#setvalidchars)有効な文字の一覧を指定します。  
  
 4. 呼び出す、 [CMFCMaskedEdit::SetWindowText](#setwindowtext)マスク エディット コントロールの既定のテキストを指定します。  
  
 5. 呼び出す、 [CMFCMaskedEdit::GetWindowText](#getwindowtext)検証済みのテキストを取得します。  
  
 マスク、有効な文字は、および既定のテキストを初期化するために 1 つまたは複数のメソッドを呼び出すことはない場合、マスク エディット コントロールは、標準的な編集コントロールの動作と同様に動作します。  
  
## <a name="example"></a>例  
 次の例を使用してマスク (電話番号など) を設定する方法、`EnableMask`マスク エディット コントロールでは、マスクを作成する方法、`SetValidChars`ユーザーが入力できる、有効な文字との文字列を指定する方法`SetWindowText`マスクのプロンプトを表示する方法は、コントロールを編集します。 この例の一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmaskededit.h  
  
##  <a name="disablemask"></a>  CMFCMaskedEdit::DisableMask  
 ユーザー入力の検証を無効にします。  
  
```  
void DisableMask();
```  
  
### <a name="remarks"></a>コメント  
 ユーザー入力の検証が無効になっている場合、標準的な編集コントロールと同様に、マスク エディット コントロールが動作します。  
  
##  <a name="enablegetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 指定するかどうか、`GetWindowText`メソッドは、マスクされた文字のみを取得します。  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` 指定する、 [CMFCMaskedEdit::GetWindowText](#getwindowtext)メソッド取得のみマスクされた文字です。`FALSE`メソッドがテキスト全体を取得することを指定します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 マスクされた文字の取得を有効にするのにには、このメソッドを使用します。 次 (425) 555-0187 などの電話番号に対応するマスク エディット コントロールを作成します。 呼び出す場合は、`GetWindowText`メソッド、「4255550187」返します。 マスクされた文字を取得するを無効にする場合、`GetWindowText`メソッド「(425) 555-0187」などのエディット コントロールに表示されるテキストを返します。  
  
##  <a name="enablemask"></a>  CMFCMaskedEdit::EnableMask  
 編集コントロールのマスクを初期化します。  
  
```  
void EnableMask(
    LPCTSTR lpszMask,  
    LPCTSTR lpszInputTemplate,  
    TCHAR chMaskInputTemplate=_T('_'),  
    LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszMask`  
 ユーザー入力の各位置で表示できる文字の種類を指定するマスク文字列。 長さ、`lpszInputTemplate`と`lpszMask`パラメーター文字列は同じである必要があります。 マスク文字の詳細については「解説」セクションを参照してください。  
  
 [入力] `lpszInputTemplate`  
 リテラル文字を指定するマスク テンプレート文字列は、ユーザー入力の各位置で表示できます。 文字のプレース ホルダーとして、アンダー スコア文字 ('_') を使用します。 長さ、`lpszInputTemplate`と`lpszMask`パラメーター文字列は同じである必要があります。  
  
 [入力] `chMaskInputTemplate`  
 各ユーザー入力に無効な文字の代わりの既定の文字です。 このパラメーターの既定値は、アンダー スコア (_) です。  
  
 [入力] `lpszValid`  
 有効な文字のセットを含む文字列。 `NULL` すべての文字が有効であることを示します。 このパラメーターの既定値は、`NULL` です。  
  
### <a name="remarks"></a>コメント  
 マスク エディット コントロールのマスクを作成するのにには、このメソッドを使用します。 クラスを派生、`CMFCMaskedEdit`クラスし、オーバーライド、 [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)カスタム マスク処理に独自のコードを使用する方法です。  
  
 次の表は、既定のマスク文字を一覧表示します。  
  
|マスク文字|定義|  
|--------------------|----------------|  
|D|数字です。|  
|d|数字またはスペース。|  
|+|プラス記号 ('+ ')、マイナス ('-')、または領域です。|  
|C|アルファベット文字。|  
|c|アルファベット文字またはスペース。|  
|A|英数字文字。|  
|a|英数字文字またはスペース。|  
|*|印刷可能な文字です。|  
  
##  <a name="enableselectbygroup"></a>  CMFCMaskedEdit::EnableSelectByGroup  
 マスク エディット コントロールがユーザーに特定グループの選択の入力、またはすべての入力を許可するかどうかを指定します。  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` グループのみを選択するには`FALSE`全体のテキストを選択します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 マスク エディット コントロールに、ユーザー グループまたはテキスト全体を選択できるかどうかを指定するのにには、この関数を使用します。  
  
 既定では、グループでの選択が有効にします。 ここでは、ユーザーは、有効な文字の連続するグループのみを選択できます。  
  
 たとえば、次のマスク エディット コントロールを使用して、電話番号を検証する可能性があります。  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 グループでの選択が有効になっている場合、ユーザーはのみ「425」、「555」または「0187」文字列のグループを取得できます。 グループの選択が無効になっている場合、ユーザーが電話番号のテキスト全体を取得できます:「(425) 555-0187」です。  
  
##  <a name="enablesetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 指定マスク文字だけまたはマスク全体にテキストを検証するかどうか。  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` ユーザーを検証する入力に対してのみマスク文字です。`FALSE`マスク全体を検証します。 既定値は `TRUE` です。  
  
##  <a name="getwindowtext"></a>  CMFCMaskedEdit::GetWindowText  
 検証済みのマスク エディット コントロールからテキストを取得します。  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(CString& rstrString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `lpszStringBuf`  
 エディット コントロールからテキストを受け取るバッファーへのポインター。  
  
 [入力] `nMaxCount`  
 受信する文字の最大数。  
  
 [出力] `rstrString`  
 エディット コントロールからテキストを受け取る文字列オブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 最初のメソッド オーバー ロードにコピーされる文字列のバイト数を返します、`lpszStringBuf`パラメーター バッファー マスク エディット コントロールにテキストがあるない場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドにマスク エディット コントロールからのテキストのコピー、`lpszStringBuf`バッファーまたは`rstrString`文字列。  
  
 このメソッドを再定義[CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext)です。  
  
##  <a name="ismaskedchar"></a>  CMFCMaskedEdit::IsMaskedChar  
 対応するマスク文字に対して指定した文字を検証するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL IsMaskedChar(
    TCHAR chChar,  
    TCHAR chMaskChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `chChar`  
 検証に使用する文字。  
  
 [入力] `chMaskChar`  
 マスク文字列から対応する文字。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合、`chChar`パラメーターがによって許可されている文字の種類、`chMaskChar`パラメーターです。 それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 自分で入力文字を検証するのには、このメソッドをオーバーライドします。 マスク文字の詳細については、次を参照してください。、 [CMFCMaskedEdit::EnableMask](#enablemask)メソッドです。  
  
##  <a name="setvalidchars"></a>  CMFCMaskedEdit::SetValidChars  
 ユーザーが入力できる有効な文字の文字列を指定します。  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszValid`  
 有効な入力文字のセットを含む文字列。 `NULL` すべての文字が有効であることを意味します。 このパラメーターの既定値は、`NULL` です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、有効な文字の一覧を定義します。 入力文字がこの一覧にない場合は、マスク エディット コントロールは使用できません。  
  
 次のコード例では、16 進数のみを受け入れます。  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>  CMFCMaskedEdit::SetWindowText  
 マスク エディット コントロールで、プロンプトを表示します。  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszString`  
 プロンプトとして使用される null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コントロールのテキストを設定します。  
  
 このメソッドを再定義[とき](../../mfc/reference/cwnd-class.md#setwindowtext)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)
