---
description: 詳細については、「BSTR 用のメモリの割り当てと解放」を参照してください。
title: BSTR 用のメモリの割り当てと解放
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: 2b027bdc5615578bc785075ae7e8709e2b3a7ea5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142664"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>BSTR 用のメモリの割り当てと解放

を作成 `BSTR` して COM オブジェクト間で渡す場合は、メモリリークを回避するために、使用しているメモリを十分に扱う必要があります。 がインターフェイス内に保持されている場合は、操作 `BSTR` が完了したら、そのメモリを解放する必要があります。 ただし、が `BSTR` インターフェイスから渡されると、受信側のオブジェクトはそのメモリの管理に責任を持ちます。

一般に、に割り当てられたメモリの割り当てと解放の規則は次のとおりです `BSTR` 。

- 引数を必要とする関数を呼び出す場合は、 `BSTR` 呼び出しの前にのメモリを割り当ててから、後で解放する必要があり `BSTR` ます。 次に例を示します。

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- を返す関数を呼び出す場合は、 `BSTR` 自分で文字列を解放する必要があります。 次に例を示します。

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- を返す関数を実装する場合は、 `BSTR` 文字列を割り当てますが、その文字列は解放されません。 関数を受け取ると、メモリが解放されます。 次に例を示します。

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT:: AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)
