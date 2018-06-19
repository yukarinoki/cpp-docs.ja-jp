---
title: 文字列変換マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 917afc7dae7a0ed96d5d5cc476b4f8394abe8913
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362976"
---
# <a name="string-conversion-macros"></a>文字列変換マクロ

これらのマクロは、文字列の変換機能を提供します。  
 
##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL と MFC 文字列変換マクロ

ここで説明する文字列変換マクロは、ATL と MFC の両方に対して有効です。 MFC 文字列変換の詳細については、次を参照してください。 [TN059: を使用して MFC の Mbcs/unicode 変換マクロ](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md)と[MFC マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)です。

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  DEVMODE と受け取る文字列変換マクロ

これらのマクロのコピーを作成する、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)または[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)構造体し、新しい構造内の文字列を新しい文字列型に変換します。 マクロは、新しい構造のスタックにメモリを割り当て、新しい構造体へのポインターを返します。  
  
```cpp
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>コメント

例えば:  
  
[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
および  
  
[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
マクロ名、文字列型、ソース構造では左側の (たとえば、 **A**) し、右側の送信先構造での文字列型は、(たとえば、 **W**)。 **A**の略`LPSTR`、 **OLE**の略`LPOLESTR`、 **T**の略`LPTSTR`、および**W**の略`LPWSTR`です。  
  
したがって、 **DEVMODEA2W**コピー、`DEVMODE`構造体`LPSTR`に文字列、`DEVMODE`構造体`LPWSTR`文字列、 **TEXTMETRICOLE2T**コピー、 `TEXTMETRIC`構造体`LPOLESTR`に文字列を`TEXTMETRIC`構造体`LPTSTR`文字列、およびなどです。  
  
2 つの文字列に変換された、`DEVMODE`構造体は、デバイス名 (`dmDeviceName`) と形式名 (`dmFormName`)。 `DEVMODE`文字列変換マクロも構造体のサイズを更新 (`dmSize`)。  
  
4 つの文字列に変換された、`TEXTMETRIC`構造体は、最初の文字 (`tmFirstChar`)、最後の文字 (`tmLastChar`)、既定の文字 (`tmDefaultChar`)、および改行文字 (`tmBreakChar`)。
  
動作、`DEVMODE`と`TEXTMETRIC`文字列変換マクロは、存在する場合、有効なコンパイラ ディレクティブとは異なります。 します。 ソースの型とターゲットの型が同じである場合、変換は実行されません。 コンパイラ ディレクティブ**T**と**OLE**次のようにします。  
  
|有効なコンパイラ ディレクティブ|T の変更後|OLE の変更後|  
|----------------------------------|---------------|-----------------|  
|none|**A**|**W**|  
|**\_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**\_UNICODE**と**は、OLE2ANSI**|**W**|**A**|  
  
 次の表、`DEVMODE`と`TEXTMETRIC`文字列変換マクロです。  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)
