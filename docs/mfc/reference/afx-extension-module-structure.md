---
title: AFX_EXTENSION_MODULE 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6560bf337f6e146bba19e41d56727945df771dd2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349259"
---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE 構造体
`AFX_EXTENSION_MODULE` MFC 拡張 DLL のモジュールの状態を保持する MFC 拡張 Dll の初期化中に使用されます。  
  
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
 *bInitialized*  
 **TRUE**で DLL モジュールが初期化されている場合`AfxInitExtensionModule`です。  
  
 `hModule`  
 DLL のモジュールのハンドルを指定します。  
  
 *hResource*  
 DLL のカスタム リソース モジュールのハンドルを指定します。  
  
 *pFirstSharedClass*  
 情報へのポインター (、`CRuntimeClass`構造) は、DLL モジュールの最初のランタイム クラスです。 ランタイム クラスの一覧の先頭を指定するために使用します。  
  
 *pFirstSharedFactory*  
 DLL モジュールの最初のオブジェクト ファクトリへのポインター (、`COleObjectFactory`オブジェクト)。 クラス ファクトリの一覧の先頭を指定するために使用します。  
  
## <a name="remarks"></a>コメント  
 MFC 拡張 Dll で次の 2 つを行う必要性、`DllMain`関数。  
  
-   呼び出す[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)戻り値を確認します。  
  
-   作成、 **CDynLinkLibrary**オブジェクトの DLL をエクスポートするかどうかは[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)独自のカスタム リソースまたはオブジェクトします。  
  
 `AFX_EXTENSION_MODULE`構造が MFC 拡張 DLL のモジュールの状態、通常の静的オブジェクトの構築の前に実行の一部としてに MFC 拡張 DLL が初期化されたランタイム クラスのオブジェクトのコピーを含むのコピーを保持するために使用される`DllMain`は入力します。 例えば:  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 格納されているモジュールの情報、`AFX_EXTENSION_MODULE`に構造をコピーすることができます、 **CDynLinkLibrary**オブジェクト。 例えば:  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

