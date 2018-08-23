---
title: 属性付きプログラムの作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tlb files
- MIDL
- MIDL, linker output
- IDL files
- tlb files, building attributed programs
- .tlb files, building attributed programs
- IDL files, building
- attributes [C++], building type libraries and .idl files
- .tlb files
- .idl files, building
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7909884a355ccad5e1bf9d18a38dd3e4690296ee
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42587508"
---
# <a name="building-an-attributed-program"></a>属性付きプログラムの作成

Visual C 属性をソース コードに追加した後のタイプ ライブラリおよび .idl ファイルを生成するために、Visual C コンパイラをする可能性があります。 次のリンカー オプションの .tlb および .idl ファイルの構築に役立つ。

- [/IDLOUT](../build/reference/idlout-name-midl-output-files.md)

- [/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/MIDL](../build/reference/midl-specify-midl-command-line-options.md)

- [/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)

いくつかのプロジェクトには、複数の独立した .idl ファイルが含まれます。 これらは、2 つ以上の .tlb ファイルを生成し、必要に応じてリソース ブロックにバインドに使用されます。 このシナリオは、Visual C では現在サポートされていません。

さらに、Visual C リンカーは、1 つの MIDL ファイルにすべての属性の IDL に関連する情報を出力します。 1 つのプロジェクトから 2 つのタイプ ライブラリを生成する方法されません。

## <a name="see-also"></a>関連項目

[概念](../windows/attributed-programming-concepts.md)