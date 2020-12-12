---
description: '詳細情報: MFC コモンコントロールライブラリの分離'
title: MFC コモン コントロール ライブラリの分離
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
ms.openlocfilehash: f3e0f6ad981a690f6212455b8af891eaa97f2642
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335824"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>MFC コモン コントロール ライブラリの分離

コモンコントロールライブラリが MFC 内で分離されるようになりました。これにより、さまざまなモジュール (ユーザー Dll など) が異なるバージョンのコモンコントロールライブラリを使用できるようになります。そのためには、マニフェストでバージョンを指定します。

MFC アプリケーション (または MFC によって呼び出されるユーザーコード) は、FunctionName という名前のラッパー関数を使用して一般的なコントロールライブラリ Api を呼び出し `Afx` ます。ここで、 *FUNCTIONNAME* は common controls api の名前です。 これらのラッパー関数は、afxcomctl32.h と afxcomctl32.h で定義されています。

(Afxcomctl32.h で定義されている) [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) および [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) マクロを使用して、コモンコントロールライブラリが [GetProcAddress](../build/getprocaddress.md)を呼び出す代わりに特定の API を実装するかどうかを判断できます。

技術的には、 `CComCtlWrapper` (afxcomctl32.h で定義されている) ラッパークラスを使用して、コモンコントロールライブラリ api を呼び出すことができます。 `CComCtlWrapper` は、comctl32.dll の読み込みとアンロードも行います。 MFC モジュールの状態には、のインスタンスへのポインターが含まれてい `CComCtlWrapper` ます。 ラッパークラスには、マクロを使用してアクセスでき `afxComCtlWrapper` ます。

Mfc アプリケーションまたはユーザー DLL から Common Controls API を直接呼び出す (mfc ラッパー関数を使用しない) ことは、ほとんどの場合に機能します。これは、MFC アプリケーションまたはユーザー DLL が、マニフェストで要求されるコモンコントロールライブラリにバインドされるためです。 ただし、mfc コードは、異なる共通コントロールライブラリバージョンを持つユーザー Dll から呼び出される可能性があるため、ラッパーを使用する必要があります。
