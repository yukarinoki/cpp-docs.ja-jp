---
title: ファイルを編集するリソースの種類 (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- file types [C++], for resources
- resources [C++], editing
- files [C++], editable types
- resource editing
ms.assetid: c40f9204-f2f2-400b-9f53-53b7bf291356
ms.openlocfilehash: 9f688c144a3453c2de849b36f34f6a465e3dfeae
ms.sourcegitcommit: 5a7dbd640376e13379f5d5b2cf66c4842e5e737b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55905720"
---
# <a name="editable-file-types-for-resources-c"></a>ファイルを編集するリソースの種類 (C++)

次の種類のファイルを開いて、格納されているリソースを編集することができます。

|ファイル名|説明|
|---------------|-----------------|
|.rc|リソース スクリプト ファイル。|
|.rct|リソース テンプレート ファイル。|
|.res|リソース ファイル。|
|.resx|マネージド リソース ファイル。|
|.exe|実行可能ファイル。|
|.dll|ダイナミック リンク ライブラリ ファイル。|
|.bmp、.ico、.dib、.cur|ビットマップ、アイコン、ツール バー、カーソルのファイル。|

## <a name="files-affected-by-resource-editing"></a>リソースの編集によって影響を受けるファイル

Visual Studio 環境では、次の表に示すファイルがリソース編集セッション中に使用されます。

|ファイル名|説明|
|---------------|-----------------|
|Resource.h|開発環境で生成されるヘッダー ファイル。シンボル定義が含まれます。 (このファイルはソース管理に含めます。)|
|Filename.aps|高速読み込みに使用される、現在のリソース スクリプト ファイルのバイナリ バージョン。<br /><br /> リソース エディターは、.rc ファイルや resource.h ファイルを直接読み取りません。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスと同様に、シンボル以外の情報 (コメントなど) はコンパイル プロセス中に破棄されます。 .aps ファイルと .rc ファイルが一致しなくなると、そのたびに .rc ファイルが再生成されます (たとえば、[保存] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。 (通常は、含めないでください .aps ファイルでは、ソース管理。)|
|.rc|現在のプロジェクト内のリソース用のスクリプトを格納するリソース スクリプト ファイル。 このファイルは、保存するたびに .aps ファイルで上書きされます。 (このファイルはソース管理に含めます。)|

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)