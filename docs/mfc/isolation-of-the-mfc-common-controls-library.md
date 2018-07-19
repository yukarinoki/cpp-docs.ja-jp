---
title: MFC の一般的な分離コントロール ライブラリ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 193a0ea527cda3819a585f5b7149c823a7eb8ef7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346816"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>MFC コモン コントロール ライブラリの分離
コモン コントロール ライブラリが今すぐ分離 (ユーザー Dll) などのさまざまなモジュールを許可する MFC 内で独自のマニフェストでバージョンを指定することで別のバージョンのコモン コントロール ライブラリを使用します。  
  
 MFC アプリケーション (またはユーザー コードが MFC によって呼び出されます) は、ラッパー関数を使用して Api がという名前のコモン コントロール ライブラリへの呼び出し`Afx` *FunctionName*ここで、 *FunctionName*共通の名前を指定します。API を制御します。 これらのラッパー関数は、afxcomctl32.h と afxcomctl32.inl で定義されます。  
  
 使用することができます、 [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists)と[AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2)コモン コントロール ライブラリを呼び出す代わりに特定の API を実装するかどうかを確認するマクロ (で定義されている afxcomctl32.h)[GetProcAddress](../build/getprocaddress.md)です。  
  
 技術的には、ラッパー クラスを使用して一般的なコントロール ライブラリの Api への呼び出しを行う`CComCtlWrapper`(afxcomctl32.h で定義されている)。 `CComCtlWrapper` 読み込みとアンロード comctl32.dll の担当もです。 MFC モジュール状態にはインスタンスへのポインターが含まれています`CComCtlWrapper`です。 ラッパー クラスを使用して、アクセスできる、`afxComCtlWrapper`マクロです。  
  
 呼び出して共通コントロール API を直接 (MFC ラッパー関数を使用していない)、MFC からアプリケーションまたはユーザーの DLL は機能のほとんどの場合、MFC アプリケーションまたは DLL をユーザーが自らのマニフェストで要求コモン コントロール ライブラリにバインドされているため)。 ただし、MFC コード自体は、MFC コードは異なるバージョンのコモン コントロール ライブラリ Dll をユーザーから呼び出された可能性があるため、ラッパーを使用するがします。

