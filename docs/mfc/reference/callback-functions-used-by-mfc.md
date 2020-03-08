---
title: MFC で使われているコールバック関数
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 9e51774b2158a81fce05dc0bd27e296e4ad94faa
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855526"
---
# <a name="callback-functions-used-by-mfc"></a>MFC で使われているコールバック関数

Microsoft Foundation Class ライブラリに3つのコールバック関数が表示されます。 これらのコールバック関数は、 [cdc:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)、 [Cdc:: GrayString](../../mfc/reference/cdc-class.md#graystring)、および[Cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)に渡されます。 コールバックの境界を越えて例外をスローすることはできないため、すべてのコールバック関数は、Windows に戻る前に MFC 例外をトラップする必要があることに注意してください。 例外の詳細については、「[例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

|Name||
|----------|-----------------|
|[CDC::EnumObjects 用コールバック関数](#enum_objects)||
|[CDC::GrayString 用コールバック関数](#graystring)||
|[CDC::SetAbortProc 用コールバック関数](#setabortproc)||

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="enum_objects"></a>CDC:: EnumObjects のコールバック関数

*Objectfunc* name は、アプリケーションによって提供される関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>パラメーター

*lpszLogObject*<br/>
オブジェクトの論理属性に関する情報を格納している[LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen)または[logbrush](/windows/win32/api/wingdi/ns-wingdi-logbrush)データ構造体を指します。

*lpData*<br/>
`EnumObjects` 関数に渡されたアプリケーションによって提供されるデータを指します。

### <a name="return-value"></a>戻り値

コールバック関数は、 **int**を返します。この戻り値は、ユーザー定義です。 コールバック関数が0を返した場合、`EnumObjects` は初期の列挙を停止します。

### <a name="remarks"></a>解説

実際の名前をエクスポートする必要があります。

## <a name="graystring"></a>CDC:: GrayString のコールバック関数

*Outputfunc*は、アプリケーションによって提供されるコールバック関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>パラメーター

*hDC*<br/>
少なくとも `nWidth` によって指定された幅と高さのビットマップを持つメモリデバイスコンテキストを識別し、`GrayString`に `nHeight` します。

*lpData*<br/>
描画される文字列を指します。

*nCount*<br/>
出力する文字数を指定します。

### <a name="return-value"></a>戻り値

成功を示すには、コールバック関数の戻り値が TRUE である必要があります。それ以外の場合は FALSE になります。

### <a name="remarks"></a>解説

コールバック関数 (*Outputfunc*) は、(*x*, *y*) ではなく、座標 (0, 0) を基準としたイメージを描画する必要があります。

## <a name="setabortproc"></a>CDC:: SetAbortProc のコールバック関数

*Abortfunc*という名前は、アプリケーションによって提供される関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>パラメーター

*hPr*<br/>
デバイスコンテキストを識別します。

*code*<br/>
エラーが発生したかどうかを示します。 エラーが発生しなかった場合は0になります。 これは、印刷マネージャーのディスク領域が不足していて、アプリケーションが待機しているときに使用可能なディスク領域が増えた場合に SP_OUTOFDISK ます。 *コード*が SP_OUTOFDISK 場合、アプリケーションは印刷ジョブを中止する必要はありません。 そうでない場合は、`PeekMessage` または `GetMessage` Windows 関数を呼び出すことによって、印刷マネージャーに渡す必要があります。

### <a name="return-value"></a>戻り値

中止ハンドラー関数の戻り値は、印刷ジョブが続行する場合は0以外、キャンセルされた場合は0になります。

### <a name="remarks"></a>解説

[CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)の「解説」の説明に従って、実際の名前をエクスポートする必要があります。

## <a name="see-also"></a>参照

[構造体、スタイル、コールバック関数とメッセージ マップ](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC:: GrayString](../../mfc/reference/cdc-class.md#graystring)
