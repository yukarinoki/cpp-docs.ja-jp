---
title: 名前ではなく序数値による DLL 関数のエクスポート
ms.date: 11/04/2016
f1_keywords:
- NONAME
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: fe34ec90aa775e7435d4a02b9d77a9cb9c8fdd65
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423301"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>名前ではなく序数値による DLL 関数のエクスポート

DLL から関数をエクスポートする最も簡単な方法では、それらの名前でエクスポートします。 これは、使用するときに起こる**方式**など。 代わりに序数で関数をエクスポートすることができます。 この手法では、代わりに .def ファイルを使用する必要があります**方式**します。 関数の序数値を指定するには、.def ファイル内の関数名をその序数を追加します。 序数を指定する方法の詳細については、次を参照してください。 [.def ファイルを使った DLL からエクスポート](../build/exporting-from-a-dll-using-def-files.md)します。

> [!TIP]
>  DLL のファイルのサイズを最適化する場合を使用して、 **NONAME**エクスポートされた各関数の属性。 **NONAME**属性、序数に格納されている場合、DLL のエクスポート関数名ではなくテーブル。 多くの関数をエクスポートする場合は、この大幅なコストを削減できます。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [序数でエクスポートできるので、.def ファイルを使用します。](../build/exporting-from-a-dll-using-def-files.md)

- [関数を使用します。](../build/exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](../build/exporting-from-a-dll.md)
