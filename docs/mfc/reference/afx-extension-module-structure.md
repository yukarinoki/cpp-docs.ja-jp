---
description: '詳細情報: AFX_EXTENSION_MODULE 構造'
title: AFX_EXTENSION_MODULE 構造体
ms.date: 11/04/2016
f1_keywords:
- AFX_EXTENSION_MODULE
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
ms.openlocfilehash: d3a5abd449f13a06aa5d7388b2dd2926a6011973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248230"
---
# <a name="afx_extension_module-structure"></a>AFX_EXTENSION_MODULE 構造体

は、mfc 拡張 `AFX_EXTENSION_MODULE` dll モジュールの状態を保持するために、mfc 拡張 dll の初期化中に使用されます。

## <a name="syntax"></a>構文

```
struct AFX_EXTENSION_MODULE
{
    BOOL bInitialized;
    HMODULE hModule;
    HMODULE hResource;
    CRuntimeClass* pFirstSharedClass;
    COleObjectFactory* pFirstSharedFactory;
};
```

#### <a name="parameters"></a>パラメーター

*ビン分割*<br/>
DLL モジュールがで初期化されている場合は TRUE `AfxInitExtensionModule` 。

*hModule*<br/>
DLL モジュールのハンドルを指定します。

*hResource*<br/>
DLL カスタムリソースモジュールのハンドルを指定します。

*pFirstSharedClass*<br/>
`CRuntimeClass`DLL モジュールの最初のランタイムクラスに関する情報 (構造体) へのポインター。 ランタイムクラスリストの先頭を指定するために使用されます。

*pFirstSharedFactory*<br/>
DLL モジュールの最初のオブジェクトファクトリ (オブジェクト) へのポインター `COleObjectFactory` 。 クラスファクトリリストの先頭を指定するために使用されます。

## <a name="remarks"></a>解説

MFC 拡張 Dll では、関数内で次の2つの処理を行う必要があり `DllMain` ます。

- [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)を呼び出し、戻り値を確認します。

- DLL が `CDynLinkLibrary` [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトをエクスポートする場合、または独自のカスタムリソースがある場合は、オブジェクトを作成します。

`AFX_EXTENSION_MODULE`構造体は、mfc 拡張 dll モジュールの状態のコピーを保持するために使用されます。これには、が入力される前に実行される通常の静的オブジェクト構築の一部として、mfc 拡張 dll によって初期化されたランタイムクラスオブジェクトのコピーが含まれ `DllMain` ます。 次に例を示します。

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

構造体に格納されているモジュール情報を `AFX_EXTENSION_MODULE` オブジェクトにコピーでき `CDynLinkLibrary` ます。 次に例を示します。

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)
