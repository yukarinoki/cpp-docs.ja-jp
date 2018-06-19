---
title: ___lc_codepage_func | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___lc_codepage_func
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef848de1219ae86f447ddf67efb8af6b8e184cc4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390633"
---
# <a name="lccodepagefunc"></a>___lc_codepage_func
内部 CRT 関数。 スレッドの現在のコード ページを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>戻り値  
 スレッドの現在のコード ページ。  
  
## <a name="remarks"></a>コメント  
 `___lc_codepage_func` は、CRT データのスレッド ローカル ストレージから現在のコード ページを取得するために、他の CRT 関数によって使用される内部 CRT 関数です。 この情報は、[_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 関数を使用して取得することもできます。  
  
 *コード ページ*は、個別の文字への 1 バイト コードまたは 2 バイト コードのマッピングです。 異なるコード ページには異なる特殊文字が含まれ、それらは通常は 1 つの言語または言語グループ用にカスタマイズされています。 コード ページの詳細については、「 [Code Pages](../c-runtime-library/code-pages.md)」を参照してください。  
  
 内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。 コード内では使用しないことをお勧めします。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`___lc_codepage_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>参照  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)