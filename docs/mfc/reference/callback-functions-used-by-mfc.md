---
title: MFC で使われているコールバック関数
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 553e87320828590c9e1e9204b54622f2f1ca6d80
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040887"
---
# <a name="callback-functions-used-by-mfc"></a>MFC で使われているコールバック関数

Microsoft Foundation Class ライブラリに3つのコールバック関数が表示されます。 これらのコールバック関数は、 [cdc:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)、 [Cdc:: GrayString](../../mfc/reference/cdc-class.md#graystring)、および [Cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)に渡されます。 コールバックの境界を越えて例外をスローすることはできないため、すべてのコールバック関数は、Windows に戻る前に MFC 例外をトラップする必要があることに注意してください。 例外の詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

[CDC:: EnumObjects のコールバック関数](#enum_objects)\
[CDC:: GrayString のコールバック関数](#graystring)\
[CDC::SetAbortProc 用コールバック関数](#setabortproc)

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="callback-function-for-cdcenumobjects"></a><a name="enum_objects"></a> CDC:: EnumObjects のコールバック関数

*Objectfunc* name は、アプリケーションによって提供される関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>パラメーター

*lpszLogObject*<br/>
オブジェクトの論理属性に関する情報を格納している [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) または [logbrush](/windows/win32/api/wingdi/ns-wingdi-logbrush) データ構造体を指します。

*lpData*<br/>
は、関数に渡されたアプリケーションによって提供されるデータを指し `EnumObjects` ます。

### <a name="return-value"></a>戻り値

コールバック関数は、を返し **`int`** ます。 この戻り値は、ユーザー定義です。 コールバック関数が0を返した場合、は `EnumObjects` 初期の列挙を停止します。

### <a name="remarks"></a>注釈

実際の名前をエクスポートする必要があります。

## <a name="callback-function-for-cdcgraystring"></a><a name="graystring"></a> CDC:: GrayString のコールバック関数

*Outputfunc* は、アプリケーションによって提供されるコールバック関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>パラメーター

*hDC*<br/>
によって指定された幅と高さ以上のビットマップを持つメモリデバイスコンテキストをに指定し `nWidth` `nHeight` `GrayString` ます。

*lpData*<br/>
描画される文字列を指します。

*nCount*<br/>
出力する文字数を指定します。

### <a name="return-value"></a>戻り値

成功を示すには、コールバック関数の戻り値が TRUE である必要があります。それ以外の場合は FALSE になります。

### <a name="remarks"></a>注釈

コールバック関数 (*Outputfunc*) は、(*x*, *y*) ではなく、座標 (0, 0) を基準としたイメージを描画する必要があります。

## <a name="callback-function-for-cdcsetabortproc"></a><a name="setabortproc"></a> CDC:: SetAbortProc のコールバック関数

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
エラーが発生したかどうかを示します。 エラーが発生しなかった場合は0になります。 これは、印刷マネージャーのディスク領域が不足していて、アプリケーションが待機しているときに使用可能なディスク領域が増えた場合に SP_OUTOFDISK ます。 *コード*が SP_OUTOFDISK 場合、アプリケーションは印刷ジョブを中止する必要はありません。 そうでない場合は、または Windows の関数を呼び出して、印刷マネージャーに渡す必要があり `PeekMessage` `GetMessage` ます。

### <a name="return-value"></a>戻り値

中止ハンドラー関数の戻り値は、印刷ジョブが続行する場合は0以外、キャンセルされた場合は0になります。

### <a name="remarks"></a>注釈

[CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)の「解説」の説明に従って、実際の名前をエクスポートする必要があります。

## <a name="see-also"></a>参照

[構造体、スタイル、コールバック、およびメッセージマップ](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC:: GrayString](../../mfc/reference/cdc-class.md#graystring)
