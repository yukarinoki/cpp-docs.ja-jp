---
title: クラスをマスクします。
ms.date: 11/04/2016
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
ms.openlocfilehash: de28b308ec235e33e39aabd707677f4e75320b0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365282"
---
# <a name="cmfcmaskededit-class"></a>クラスをマスクします。

この`CMFCMaskedEdit`クラスはマスクエディット コントロールをサポートしており、ユーザー入力をマスクに照らして検証し、テンプレートに従って検証結果を表示します。

## <a name="syntax"></a>構文

```
class CMFCMaskedEdit : public CEdit
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCMaskedEdit::CMFCMaskedEdit`|既定のコンストラクターです。|
|`CMFCMaskedEdit::~CMFCMaskedEdit`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[:D可能なマスク](#disablemask)|ユーザー入力の検証を無効にします。|
|[をクリックします。](#enablegetmaskedcharsonly)|メソッドが`GetWindowText`マスクされた文字のみを取得するかどうかを指定します。|
|[マスクエディット::イネーブルマスク](#enablemask)|マスクエディット コントロールを初期化します。|
|[CMFCマスクエディット::有効化セレクトバイグループ](#enableselectbygroup)|マスクエディット コントロールが特定のユーザー入力グループを選択するか、すべてのユーザー入力を選択するかを指定します。|
|[::有効に設定されたマスクされた文字のみ](#enablesetmaskedcharsonly)|テキストをマスク文字のみに対して検証するか、マスク全体に対して検証するかを指定します。|
|`CMFCMaskedEdit::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ウィンドウテキストを編集します。](#getwindowtext)|マスクエディット コントロールから検証済みのテキストを取得します。|
|[編集::セットValidChars](#setvalidchars)|ユーザーが入力できる有効な文字の文字列を指定します。|
|[ウィンドウテキストを編集します。](#setwindowtext)|マスクされたエディット コントロールにプロンプトを表示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCマスクエディット::マスクドシャア](#ismaskedchar)|指定した文字を対応するマスク文字と照らし合わせて検証するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

アプリケーションでコントロールを使用するには、`CMFCMaskedEdit`次の手順を実行します。

1. オブジェクトを`CMFCMaskedEdit`ウィンドウ クラスに埋め込みます。

2. マスクを指定[するには、CMFCMaskedEdit::EnableMask](#enablemask)メソッドを呼び出します。

3. 有効な[文字のリスト](#setvalidchars)を指定するには、メソッドを呼び出します。

4. マスクエディット コントロールの既定のテキストを指定するには[、CMFCMaskedEdit::SetWindowText](#setwindowtext)メソッドを呼び出します。

5. 検証済みのテキストを取得するには[、](#getwindowtext)メソッドを呼び出します。

マスク、有効な文字、および既定のテキストを初期化するために 1 つ以上のメソッドを呼び出さない場合、マスクエディット コントロールは標準のエディット コントロールの動作と同じように動作します。

## <a name="example"></a>例

次の例は、`EnableMask`マスクエディット コントロールのマスクを作成するメソッド、ユーザーが入力できる有効な文字の文字列を指定する`SetValidChars`メソッド、およびマスクエディット コントロールにプロンプトを表示する`SetWindowText`メソッドを使用して、マスク (電話番号など) を設定する方法を示しています。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmaskededit.h

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a>:D可能なマスク

ユーザー入力の検証を無効にします。

```
void DisableMask();
```

### <a name="remarks"></a>解説

ユーザー入力の検証が無効になっている場合、マスクエディット コントロールは標準の編集コントロールと同じように動作します。

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a>をクリックします。

メソッドが`GetWindowText`マスクされた文字のみを取得するかどうかを指定します。

```
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]メソッドが[マスクされた](#getwindowtext)文字のみを取得することを指定する場合は TRUE。メソッドがテキスト全体を取得することを指定する場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

このメソッドは、マスクされた文字の取得を有効にするために使います。 次に、電話番号に対応するマスク エディット コントロール (425) 555-0187 を作成します。 このメソッドを`GetWindowText`呼び出すと、"4255550187" が返されます。 マスク文字の取得を無効にすると、`GetWindowText`メソッドはエディット コントロールに表示されるテキストを返します。例えば"(425) 555-0187"。

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a>マスクエディット::イネーブルマスク

マスクエディット コントロールを初期化します。

```
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>パラメーター

*マスク*<br/>
[in]ユーザー入力の各位置に表示できる文字の種類を指定するマスク文字列。 *パラメーター*文字列の長さは同じである必要があります*lpszMask*。 マスク文字の詳細については、「解説」を参照してください。

*テンプレートを使用します。*<br/>
[in]ユーザー入力の各位置に表示できるリテラル文字を指定するマスク テンプレート文字列。 アンダースコア文字 ('_') を文字のプレースホルダとして使用します。 *パラメーター*文字列の長さは同じである必要があります*lpszMask*。

*テンプレートを使用します。*<br/>
[in]ユーザー入力の無効な文字ごとにフレームワークが置き換える既定の文字。 このパラメータの既定値はアンダースコア ('_') です。

*lpszValid*<br/>
[in]有効な文字のセットを含む文字列。 NULL は、すべての文字が有効であることを示します。 このパラメーターのデフォルト値は NULL です。

### <a name="remarks"></a>解説

このメソッドは、マスクエディット コントロールのマスクを作成するために使います。 クラスからクラスを`CMFCMaskedEdit`派生させ、カスタム マスク処理に独自のコードを使用する[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)メソッドをオーバーライドします。

次の表は、デフォルトのマスク文字を示しています。

|マスク文字|定義|
|--------------------|----------------|
|D|桁。|
|d|数字またはスペース。|
|+|プラス ('+')、マイナス('-)、またはスペース。|
|C|アルファベット文字。|
|c|英字またはスペース。|
|A|英数字。|
|a|英数字またはスペース。|
|*|印刷可能文字。|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a>CMFCマスクエディット::有効化セレクトバイグループ

マスクエディット コントロールで、ユーザーが特定のグループ入力を選択できるようにするか、すべての入力を選択するかを指定します。

```
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]グループのみを選択する場合は TRUE。テキスト全体を選択する場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

この関数を使用して、マスクエディット コントロールで、ユーザーがグループまたはテキスト全体で選択できるかどうかを指定します。

既定では、グループによる選択は有効になっています。 この場合、ユーザーは有効な文字の連続したグループのみを選択できます。

たとえば、次のマスク エディット コントロールを使用して電話番号を検証できます。

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

グループによる選択が有効になっている場合、ユーザーは"425"、"555"、または "0187" の文字列グループのみを取得できます。 グループ選択が無効になっている場合、ユーザーは電話番号のテキスト全体を取得できます。

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a>::有効に設定されたマスクされた文字のみ

テキストをマスク文字のみに対して検証するか、マスク全体に対して検証するかを指定します。

```
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]マスクされた文字に対してユーザー入力を検証する場合は TRUE。マスク全体に対して検証する場合は FALSE。 既定値は TRUE です。

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a>ウィンドウテキストを編集します。

マスクエディット コントロールから検証済みのテキストを取得します。

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>パラメーター

*lpsz ストリングブフ*<br/>
[アウト]エディット コントロールからテキストを受け取るバッファーへのポインター。

*カウントカウント*<br/>
[in]受信する最大文字数。

*文字列*<br/>
[アウト]エディット コントロールからテキストを受け取る文字列オブジェクトへの参照。

### <a name="return-value"></a>戻り値

最初のメソッドオーバーロードは *、lpszStringBuf*パラメーター バッファーにコピーされる文字列のバイト数を返します。マスクエディット コントロールにテキストがない場合は 0。

### <a name="remarks"></a>解説

このメソッドは、マスクエディット コントロールから*lpszStringBuf*バッファーまたは*rstrString*文字列にテキストをコピーします。

このメソッドは[、CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext)を再定義します。

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a>CMFCマスクエディット::マスクドシャア

指定した文字を対応するマスク文字と照らし合わせて検証するために、フレームワークによって呼び出されます。

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>パラメーター

*chChar*<br/>
[in]検証する文字。

*クマスクチャル*<br/>
[in]マスク文字列の対応する文字。

### <a name="return-value"></a>戻り値

*true の場合、chChar*パラメーターが*chMaskChar*パラメーターで許可されている文字の型です。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

入力文字を独自に検証するには、このメソッドをオーバーライドします。 マスク文字の詳細については[、「CMFCMaskedEdit::EnableMask メソッド」を参照してください](#enablemask)。

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a>編集::セットValidChars

ユーザーが入力できる有効な文字の文字列を指定します。

```
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszValid*<br/>
[in]有効な入力文字のセットを含む文字列。 NULL は、すべての文字が有効であることを意味します。 このパラメーターのデフォルト値は NULL です。

### <a name="remarks"></a>解説

このメソッドは、有効な文字のリストを定義するために使います。 入力文字がこのリストにない場合、マスクエディット コントロールはそれを受け入れません。

16 進数のみを受け入れるコード例を次に示します。

```cpp
//Mask: 0xFFFF
m_wndMaskEdit.EnableMask(
    _T(" AAAA"),                // The mask string.
    _T("0x____"),               // The literal template string.
    _T('_'));                   // The default character that
                                // replaces the backspace character.
// Valid string characters
m_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));
```

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a>ウィンドウテキストを編集します。

マスクされたエディット コントロールにプロンプトを表示します。

```
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
[in]プロンプトとして使用される null で終わる文字列へのポイント。

### <a name="remarks"></a>解説

このメソッドは、コントロール テキストを設定します。

このメソッドは[、CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)を再定義します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)
