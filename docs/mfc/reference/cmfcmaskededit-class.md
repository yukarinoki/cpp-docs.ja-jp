---
description: '詳細情報: CMFCMaskedEdit クラス'
title: CMFCMaskedEdit クラス
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
ms.openlocfilehash: 7ac61240e2941eafbbac3cbb03a4884e282cbca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265156"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit クラス

クラスはマスクエディットコントロールをサポートしており `CMFCMaskedEdit` 、マスクに対してユーザー入力を検証し、テンプレートに従って検証結果を表示します。

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
|[CMFCMaskedEdit::D isableMask](#disablemask)|ユーザー入力の検証を無効にします。|
|[CMFCMaskedEdit:: EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|`GetWindowText`メソッドがマスクされた文字のみを取得するかどうかを指定します。|
|[CMFCMaskedEdit:: EnableMask](#enablemask)|マスクエディットコントロールを初期化します。|
|[CMFCMaskedEdit:: EnableSelectByGroup](#enableselectbygroup)|マスクエディットコントロールで、特定のユーザー入力グループを選択するか、すべてのユーザー入力を選択するかを指定します。|
|[CMFCMaskedEdit:: EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|マスクされた文字のみ、またはマスク全体に対してテキストを検証するかどうかを指定します。|
|`CMFCMaskedEdit::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCMaskedEdit:: GetWindowText](#getwindowtext)|マスクされたエディットコントロールから検証済みのテキストを取得します。|
|[CMFCMaskedEdit:: SetValidChars](#setvalidchars)|ユーザーが入力できる有効な文字の文字列を指定します。|
|[CMFCMaskedEdit:: SetWindowText](#setwindowtext)|マスクエディットコントロールにプロンプトを表示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCMaskedEdit:: IsMaskedChar](#ismaskedchar)|指定された文字を対応するマスク文字に対して検証するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

アプリケーションでコントロールを使用するには、次の手順を実行し `CMFCMaskedEdit` ます。

1. オブジェクトを `CMFCMaskedEdit` ウィンドウクラスに埋め込みます。

2. マスクを指定するには、 [CMFCMaskedEdit:: EnableMask](#enablemask) メソッドを呼び出します。

3. [CMFCMaskedEdit:: SetValidChars](#setvalidchars)メソッドを呼び出して、有効な文字の一覧を指定します。

4. [CMFCMaskedEdit:: SetWindowText](#setwindowtext)メソッドを呼び出して、マスクエディットコントロールの既定のテキストを指定します。

5. [CMFCMaskedEdit:: GetWindowText](#getwindowtext)メソッドを呼び出して、検証されたテキストを取得します。

マスク、有効な文字、および既定のテキストを初期化するために1つ以上のメソッドを呼び出さない場合、マスクエディットコントロールは、標準のエディットコントロールと同じように動作します。

## <a name="example"></a>例

次の例では、マスクされたエディットコントロールのマスクを作成するメソッドを使用してマスク (電話番号など) を設定する方法、 `EnableMask` `SetValidChars` ユーザーが入力できる有効な文字の文字列を指定するメソッド、マスクされた `SetWindowText` エディットコントロールにプロンプトを表示する方法を示します。 この例は、「 [新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxmaskededit

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a> CMFCMaskedEdit::D isableMask

ユーザー入力の検証を無効にします。

```cpp
void DisableMask();
```

### <a name="remarks"></a>解説

ユーザー入力の検証が無効になっている場合、マスクエディットコントロールは標準の編集コントロールのように動作します。

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a> CMFCMaskedEdit:: EnableGetMaskedCharsOnly

`GetWindowText`メソッドがマスクされた文字のみを取得するかどうかを指定します。

```cpp
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
から [CMFCMaskedEdit:: GetWindowText](#getwindowtext) メソッドがマスクされた文字だけを取得するように指定する場合は TRUE。メソッドがテキスト全体を取得するように指定する場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

マスクされた文字を取得できるようにするには、このメソッドを使用します。 次に、電話番号に対応するマスクエディットコントロールを作成します ((425) 555-0187 など)。 メソッドを呼び出すと `GetWindowText` 、"4255550187" が返されます。 マスク文字の取得を無効にした場合、メソッドは、 `GetWindowText` エディットコントロールに表示されるテキスト ("(425) 555-0187" など) を返します。

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a> CMFCMaskedEdit:: EnableMask

マスクエディットコントロールを初期化します。

```cpp
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszMask*<br/>
からユーザー入力の各位置に表示できる文字の種類を指定するマスク文字列。 *Lpszinputtemplate* パラメーターと *lpszmask* パラメーターの文字列の長さは同じである必要があります。 マスク文字の詳細については、「解説」を参照してください。

*lpszInputTemplate*<br/>
からユーザー入力の各位置に表示できるリテラル文字を指定するマスクテンプレート文字列。 文字のプレースホルダーとしてアンダースコア文字 (' _ ') を使用します。 *Lpszinputtemplate* パラメーターと *lpszmask* パラメーターの文字列の長さは同じである必要があります。

*chMaskInputTemplate*<br/>
からユーザー入力内の無効な文字ごとにフレームワークが置き換える既定の文字。 このパラメーターの既定値はアンダースコア (' _ ') です。

*lpszValid*<br/>
から有効な文字のセットを含む文字列。 NULL は、すべての文字が有効であることを示します。 このパラメーターの既定値は NULL です。

### <a name="remarks"></a>解説

マスクされたエディットコントロールのマスクを作成するには、このメソッドを使用します。 クラスからクラスを派生させ、 `CMFCMaskedEdit` [CMFCMaskedEdit:: IsMaskedChar](#ismaskedchar) メソッドをオーバーライドして、カスタムマスク処理に独自のコードを使用します。

次の表に、既定のマスク文字の一覧を示します。

|マスク文字|定義|
|--------------------|----------------|
|D|数値.|
|d|数字またはスペース。|
|+|プラス (' + ')、マイナス ('-')、または空白。|
|C|英文字。|
|c|英文字またはスペース。|
|A|英数字。|
|a|英数字または空白文字。|
|*|印刷可能な文字。|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a> CMFCMaskedEdit:: EnableSelectByGroup

マスクされたエディットコントロールで、ユーザーが特定のグループの入力またはすべての入力を選択できるようにするかどうかを指定します。

```cpp
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からグループのみを選択する場合は TRUE。テキスト全体を選択する場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

マスクされたエディットコントロールで、ユーザーがグループまたはテキスト全体を選択できるようにするかどうかを指定するには、この関数を使用します。

既定では、[グループによる選択] が有効になっています。 この場合、ユーザーは有効な文字の連続グループのみを選択できます。

たとえば、次のマスクエディットコントロールを使用して、電話番号を検証することができます。

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

グループによる選択が有効になっている場合、ユーザーは、"425"、"555"、または "0187" の文字列グループのみを取得できます。 グループの選択が無効になっている場合、ユーザーは電話番号 "(425) 555-0187" のテキスト全体を取得できます。

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a> CMFCMaskedEdit:: EnableSetMaskedCharsOnly

マスクされた文字のみ、またはマスク全体に対してテキストを検証するかどうかを指定します。

```cpp
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からマスクされた文字に対してのみユーザー入力を検証する場合は TRUE。マスク全体に対して検証する場合は FALSE。 既定値は TRUE です。

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a> CMFCMaskedEdit:: GetWindowText

マスクされたエディットコントロールから検証済みのテキストを取得します。

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>パラメーター

*lpszStringBuf*<br/>
入出力エディットコントロールからテキストを受け取るバッファーへのポインター。

*nMaxCount*<br/>
から受信する最大文字数。

*rstrString*<br/>
入出力エディットコントロールからテキストを受け取る文字列オブジェクトへの参照。

### <a name="return-value"></a>戻り値

最初のメソッドオーバーロードは、 *Lpszstringbuf* パラメーターバッファーにコピーされる文字列のバイト数を返します。マスクされたエディットコントロールにテキストがない場合は0。

### <a name="remarks"></a>解説

このメソッドは、マスクされたエディットコントロールのテキストを *Lpszstringbuf* バッファーまたは *rstrString* 文字列にコピーします。

このメソッド [は、CWnd:: GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext)を再定義します。

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a> CMFCMaskedEdit:: IsMaskedChar

指定された文字を対応するマスク文字に対して検証するために、フレームワークによって呼び出されます。

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>パラメーター

*chChar*<br/>
から検証対象の文字。

*chMaskChar*<br/>
からマスク文字列の対応する文字。

### <a name="return-value"></a>戻り値

*Chchar* パラメーターが *chmaskchar* パラメーターで許可されている文字の型である場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

独自の入力文字を検証するには、このメソッドをオーバーライドします。 マスク文字の詳細については、「 [CMFCMaskedEdit:: EnableMask](#enablemask) メソッド」を参照してください。

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a> CMFCMaskedEdit:: SetValidChars

ユーザーが入力できる有効な文字の文字列を指定します。

```cpp
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszValid*<br/>
から有効な入力文字のセットを格納している文字列。 NULL は、すべての文字が有効であることを意味します。 このパラメーターの既定値は NULL です。

### <a name="remarks"></a>解説

有効な文字の一覧を定義するには、このメソッドを使用します。 入力文字がこの一覧にない場合、マスクエディットコントロールはそれを受け入れません。

次のコード例では、16進数のみを受け入れます。

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

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a> CMFCMaskedEdit:: SetWindowText

マスクエディットコントロールにプロンプトを表示します。

```cpp
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*lpszString*<br/>
からは、プロンプトとして使用される、null で終わる文字列を指します。

### <a name="remarks"></a>解説

このメソッドは、コントロールテキストを設定します。

このメソッドは、 [CWnd:: SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)を再定義します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)
