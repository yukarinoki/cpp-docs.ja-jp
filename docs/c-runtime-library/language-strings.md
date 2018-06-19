---
title: 言語識別文字列| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92ad129a5703f509cfd9543497cceffae3a6e7b3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391364"
---
# <a name="language-strings"></a>Language Strings
`setlocale` 関数と `_create_locale` 関数は、Unicode コード ページを使用しない、オペレーティング システムの Windows NLS API によってサポートされている言語を使用できます。 オペレーティング システムのバージョンによってサポートされている言語の一覧については、[各国語サポートの (NLS) の API リファレンス](https://www.microsoft.com/resources/msdn/goglobal/default.mspx)に関するページをご覧ください。 言語識別文字列は、サポート対象の言語の一覧の **[Language]** と **[Language name abbreviation]** の列の値のいずれかです。 オペレーティング システムのバージョンごとの言語サポートに関する詳細については、[MS-LCID]: Windows Language Code Identifier (LCID) Reference ([MS-LCID]: Windows 言語コード識別子 (LCID) リファレンス) の「[Appendix A: Product Behavior (付録 A: 製品の動作)](http://msdn.microsoft.com/goglobal/bb896001.aspx)」をご覧ください。   
  
C ランタイム ライブラリの実装では、以下の言語識別文字列がサポートされます。  
  
|言語識別文字列|同等のロケール名|  
|---------------------|----------------------------|  
|american|en-US|  
|american english|en-US|  
|american-english|en-US|  
|australian|en-AU|  
|belgian|nl-BE|  
|canadian|en-CA|  
|chh|zh-HK|  
|chi|zh-SG|  
|chinese|zh|  
|chinese-hongkong|zh-HK|  
|chinese-simplified|zh-CN|  
|chinese-singapore|zh-SG|  
|chinese-traditional|zh-TW|  
|dutch-belgian|nl-BE|  
|english-american|en-US|  
|english-aus|en-AU|  
|english-belize|en-BZ|  
|english-can|en-CA|  
|english-caribbean|en-029|  
|english-ire|en-IE|  
|english-jamaica|en-JM|  
|english-nz|en-NZ|  
|english-south africa|en-ZA|  
|english-trinidad y tobago|en-TT|  
|english-uk|en-GB|  
|english-us|en-US|  
|english-usa|en-US|  
|french-belgian|fr-BE|  
|french-canadian|fr-CA|  
|french-luxembourg|fr-LU|  
|french-swiss|fr-CH|  
|german-austrian|de-AT|  
|german-lichtenstein|de-LI|  
|german-luxembourg|de-LU|  
|german-swiss|de-CH|  
|irish-english|en-IE|  
|italian-swiss|it-CH|  
|norwegian|Ｘ|  
|norwegian-bokmal|nb-NO|  
|norwegian-nynorsk|nn-NO|  
|portuguese-brazilian|pt-BR|  
|spanish-argentina|es-AR|  
|spanish-bolivia|es-BO|  
|spanish-chile|es-CL|  
|spanish-colombia|es-CO|  
|spanish-costa rica|es-CR|  
|spanish-dominican republic|es-DO|  
|spanish-ecuador|es-EC|  
|spanish-el salvador|es-SV|  
|spanish-guatemala|es-GT|  
|spanish-honduras|es-HN|  
|spanish-mexican|es-MX|  
|spanish-modern|es-ES|  
|spanish-nicaragua|es-NI|  
|spanish-panama|es-PA|  
|spanish-paraguay|es-PY|  
|spanish-peru|es-PE|  
|spanish-puerto rico|es-PR|  
|spanish-uruguay|es-UY|  
|spanish-venezuela|es-VE|  
|swedish-finland|sv-FI|  
|swiss|de-CH|  
|uk|en-GB|  
|us|en-US|  
|usa|en-US|  
  
## <a name="see-also"></a>参照  
 [ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [国/地域別文字列](../c-runtime-library/country-region-strings.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)