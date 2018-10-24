---
title: IDL 属性、メソッド追加ウィザード | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.idlattrib
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce9042a980190bf1fe3da06fb4a9843f73294dee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398847"
---
# <a name="idl-attributes-add-method-wizard"></a>IDL 属性、メソッド追加ウィザード

メソッド追加ウィザードのこのページを使用して、メソッドのインターフェイス定義言語 (IDL) 設定を指定します。

- **ID**

   メソッドを識別する数値 ID を設定します。 *MIDL リファレンス*の [id](/windows/desktop/Midl/id) に関するページを参照してください。

   このボックスは、カスタム インターフェイスでは使用不可であり、MFC ディスパッチ インターフェイスで使用することはできません。

- **call_as**

   このローカル メソッドをマップできるリモート メソッドの名前を指定します。 *MIDL リファレンス*の [call_as](/windows/desktop/Midl/call-as) に関するページを参照してください。

   MFC ディスパッチ インターフェイスでは使用できません。

- **helpcontext**

   コンテキスト ID を指定します。ユーザーはヘルプ ファイルでこのメソッドに関する情報を参照できます。 *MIDL リファレンス*の [helpcontext](/windows/desktop/Midl/helpcontext) に関するページを参照してください。

   MFC ディスパッチ インターフェイスでは使用できません。

- **helpstring**

   適用先となる要素を記述するために使用される文字列を指定します。 既定では、"メソッド <*メソッド名*>" に設定されます。 *MIDL リファレンス*の [helpstring](/windows/desktop/Midl/helpstring) に関するページを参照してください。

   MFC ディスパッチ インターフェイスでは使用できません。

- **追加の属性**

   MFC ディスパッチ インターフェイスでは使用できません。

   |属性|説明|
   |---------------|-----------------|
   |**hidden**|メソッドは存在するが、ユーザー指向ブラウザーでは表示されないことを示します。 *MIDL リファレンス*の [hidden](/windows/desktop/Midl/hidden) に関するページを参照してください。|
   |**source**|メソッドのメンバーがイベントのソースであることを示します。 *MIDL リファレンス* の [source](/windows/desktop/Midl/source) に関するページを参照してください。|
   |`local`|メソッドがリモートでないことを MIDL コンパイラに対して指定します。 *MIDL リファレンス* の [local](/windows/desktop/Midl/local) に関するページを参照してください。|
   |**restricted**|メソッドを任意に呼び出せないことを指定します。 *MIDL リファレンス* の [restricted](/windows/desktop/Midl/restricted) に関するページを参照してください。|
   |**vararg**|メソッドが可変個の引数を取ることを指定します。 そのためには、最後の引数が、残りのすべての引数を含む**バリアント**型のセーフ配列である必要があります。 *MIDL リファレンス* の [vararg](/windows/desktop/Midl/vararg) に関するページを参照してください。|

## <a name="see-also"></a>参照

[メソッドの追加](../ide/adding-a-method-visual-cpp.md)<br>
[メソッド追加ウィザード](../ide/add-method-wizard.md)