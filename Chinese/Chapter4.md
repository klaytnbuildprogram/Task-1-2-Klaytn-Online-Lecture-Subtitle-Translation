# 4. Developing an addition game with Klaytn Tools
## 4.1 Intro
 

嗨，大家好。在本教程中，我将尝试使用Klaytn区块链开发一个名为简单加法游戏的BApp。作为参考，BApp是Blockchain Applications的首字母缩写。让我们创建一个简单的弹出式游戏，如果您在3秒内解决了添加问题，将免费支付0.1 Klay。
 
 
让我们来看看它是如何工作的。首先，登录操作员帐户。我们将使用密钥库文件和密码组合验证帐户。因此，选择密钥库文件并输入密码。验证帐户后，使用Send KLAY to Contract按钮设置要用于此活动的总金额。我们将KLAY发送到合同地址的原因是以透明的方式向用户显示用于此事件的金额。请注意，这只能通过运营商帐户完成。


我现在正在发送合同。我发送约1KLAY。交易完成后，将向用户显示在活动上花费的金额。像这样。现在用户可以开始添加游戏了。如果您在3秒内设置，将从合同中将0.1 KLAY发送到用户帐户。让我们开始吧。
如果解决方法在执行此操作时出错，则会再次重置。如果再试一次，如果你解决了，你可以按OK按钮获得KLAY。交易完成后，合同中的余额减少0.1。如您所见，事务处理速度非常快。这是Klaytn的一个强项。如果单击下面的链接，您将进入Klaytn范围，在那里您可以看到刚刚创建的事务的信息。


如果您有开发以太坊DApp的经验，即将开始的课程将非常简单。 Klaytn是拜占庭版以太坊的平台，所以你会在很多方面感到熟悉。例如，可以与Klaytn区块链通信的JavaScript库caver.js类似于以太坊的web3.js.此外，我们支持最常用于智能合约开发的可靠性语言。最后，

 
因为它使用的是Truffle框架，所以可以快速适应BApp的发展。那些没有开发BApp经验的人可以通过这个练习在Klaytn区块链平台上开发BApp。但首先，理解作为智能合约开发语言的基本区块链和可靠性是很好的。我把一个链接学习。
是的，我们将开发一些支持Klaytn的工具，
首先，我编写了一个可以测试智能开发的IDE，
可以管理帐户的钱包，
让我们使用范围搜索引擎来查找交易信息。

 
 
## 4.2 Klaytn Wallet & account management
 


要使用区块链网络，您必须拥有自己的帐户。您需要一个银行帐户来管理您的KLAY令牌。所以我将使用Klaytn的钱包。它用户友好，非常易于使用。

https://baobab.klaytnwallet.com/

如果您转到此地址，则可以连接到Baobab网络并创建和管理您的帐户。作为参考，这个钱包是出于测试目的，这里使用的Klay没有货币价值。首先，让我们创建一个新帐户。单击“创建新钱包”。这是一个创建密码和密钥库文件的过程。在此之前，我将解释密钥库文件是什么。就像我们现在正在去银行制作银行存折一样，我们会把它存放在保险箱中，以便其他人不能使用它。此保管库是密钥库文件和密码组合，用于保护交易签名所需的密钥，防止黑客和外部入侵。



现在，让我们继续并创建一个密钥库文件。在此输入您的密码，单击下一步，然后下载密钥库文件。下载
然后我会告诉我的下一个屏幕在某处保存我的密钥。这里的密钥是在Klaytn BApp中签署交易的基本要求。这个密钥永远不应暴露在外面。这就像离开我的银行存折和银行存折密码并丢失所有金额。
 


这就是为什么我创建一个密钥库文件来保护我的密钥。在访问密钥之前，必须知道密钥库文件和密钥库密码。即使黑客获得密钥库文件，如果他不知道密钥，也无法访问密钥并且他无法获得金钱。这并不意味着你可以轻松摆脱密钥库。不要将它暴露在外面。
现在我将在记事本中保存此密钥。这不一定是这种情况，但它是一个测试网，我会为方便起见。您可以将私钥保存在您感到安全的地方。保存后，单击左侧的视图钱包信息。现在我可以访问我的钱包，我的钱包了。有两种方法可以解决它。第一种是使用密钥，第二种是访问密钥库文件和密码。首先，让我们使用密钥访问它。将其复制并粘贴到记事本中。

 
我的电子钱包信息现已推出。这是我的帐户公共地址和下面的密钥。我可以看到我的交易清单。我没有必要处理这个因为我还没有交易。在右侧，我可以看到我有多少KLAY，我也可以通过点击加号按钮为我的钱包添加一个令牌。
 
现在让我们在我的帐户上获取KLAY。点击KLAY水龙头标签获得免费的klay。我当前的帐户地址余额为零。如果按下“运行龙头”按钮，您将收到5个KLAY。收到后，您可以在24小时内再次收到。由于您无法在短时间内获得许多KLAY，因此您应该在测试时尽可能多地拆分KLAY。我们24小时后得到它的原因是有些人一直在使用这个KLAY被认定是恶意使用KLAY。 Klaytn说他们正在努力，所以它会更好。现在让我们将KLAY转移到另一个帐户。
 


如果您转到发送克莱和令牌标签，您可以从我的地址汇款到另一个地址。输入收件人地址。我将在底部发送一个KLAY来决定花多少钱。它说0.000625 KLAY将以下面的交易费限制出去。这就像支付佣金一样。如何衡量这一成本等于天然气价格乘以天然气限制。您可以将天然气价格视为向共识节点询问交易所支付的资金。与以太坊不同，Klaytn的汽油价格总是固定的。由于以太坊的天然气价格波动，很难预测总佣金成本。但是，无论您处理什么交易，Klaytn的天然气价格总是固定在25美元。

 

天然气限制是处理此交易的天然气的最高成本。例如，假设我们在发送的事务中有一些无限循环。然后这个简单的事务将继续在网络中运行。这会导致网络性能下降。你不应该伤害每个人。所以，如果你有超过25,000气体，你认为有些东西是奇怪的，你必须停止处理。



据说天然气价格包含25个test_ston，ston是KLAY的货币单位之一。就像美国的一美元是100美分一样，KLAY有很多单位。

https://docs.klaytn.com/klaytn/design/computation/exec_model 


Klaytn官方文件显示了KLAY单位。有很多事情。中间有一个标准的KLAY单元，顶部的peb是代表KLAY的最小单位。用于第10轮peb的单位是ston。那么25 ston转换为klay是什么。

https://blockchains.tools/pebConverter?l=KLAY 

如果你来到这个网站，你将转换许多单位。如果你把25放在斯通，KLAY就会得到这个。如果气体限制25000乘以此值，则0.000625 KLAY将出现。它用作交易费用。我们用计算器试试吧。如果您将其复制并乘以计算器气体限制25000，则会产生交易成本。这是处理交易的成本。


请注意，当您从Klaytn发送这些简单的汇款时，交易成本始终固定为0.000625 KLAY。然而，交易成本并不是通过智能合约功能在交易中固定的，因为天然气限制根据交易的复杂性而变化。我稍后会详细解释这个问题。
 
您可以通过单击旁边的“编辑”按钮手动更改价格。但我建议您继续使用默认设置。
我们现在尝试发送交易。在下一页，您将看到有关您向某人发送了多少以及交易成本将会增加多少的信息。单击是以“是否要继续？”问题，然后在一眨眼间完成交易。然后单击查看交易信息，我们发送给您的内容将保存在块中并显示给用户。我将在后面更详细地解释这一点。到目前为止，我使用过Klaytn钱包。

 

## 4.3 Klaytn IDE & Smart Contract 1
 
使用Klaytn提供的IDE，让我们为我们的附加游戏创建一个简单的智能合约。我不会专注于智能合约，而是专注于Klaytn工具。

您可以访问 http://ide.klaytn.net/ 来创建和测试智能合约。它类似于以太坊的混音IDE，但在这里它用于连接到Klaytn节点，而不是连接到以太坊节点。现在让我们通过为我们的附加游戏创建自己的智能合约来了解Klaytn IDE的功能。
 
作为参考，智能合约被称为英语智能合约。我将在课堂上将其称为“合同”。如果你看这里，你已经默认创建了一个计数合约。我会删除它并开始。请删除它。正如您在顶部的注释中所看到的，Klaytn IDE编写了Solidity 0.4.24版本，因此您必须继续使用此版本。
 
我们的合同有三个功能。第一个是将KLAY发送到合同，第二个是加载合同的余额，最后是将KLAY从合同发送到用户帐户的功能。我们将逐个制作并使用这些工具进行测试。首先，让我们将合同命名为AdditionGame。合约版游戏
 
在部署时，您将创建一个状态变量，该变量可以存储操作员帐户的地址。我正在创建一个构造函数。在此之前，构造函数通常做什么？是。它主要负责初始化。在可靠性的情况下，您无法再次编写或加载构造函数，尤其是因为它是部署时首次加载的构造函数。我可以利用这个并为合同所有者建立一个帐户。首先，我们创建状态变量所有者。类型是地址类型。我正在构建一个构造函数。所有者是消息。发件人。
 
我刚刚创建了一个构造函数。 msg.sender是当前调用此上下文的人。构造函数中的Msg.sender表示用于部署的帐户。因此，我将该帐户分配给所有者状态变量并将其永久保存到区块链中。这是初始化。所以让我们测试一下我们刚刚添加的代码。你需要先编译。单击右侧面板顶部的“自动”复选框，每次编写代码时自动编译。首先，您必须单击编译按钮以查看它是否编译。是的，编译的信息在底部。让我们再次设置环境。环境有几种选择可供选择：DEV NODE和Baobab。我可以添加一个新的网络。添加新网络功能连接到Klaytn节点当前正在运行的rpc地址并对其进行测试。我将跳过这一部分一次。 Dev节点是连接和测试Klaytn提供的开发节点的选项。它创建一个随机帐户，允许您预订100个KLAY。并且它将耗尽用于测试的气体。因此，如果您在下方的帐户中看到此帐户中已有100个测试KLAY。连接到Baobab的选项也连接到官方测试网。当您选择Baobab时，下面帐户中的KLAY会变为零。 Dev节点和baobab节点彼此独立地操作，因此在相同地址处的帐户彼此被识别，但是帐户的状态是不同的，因为节点是不同的。所以平衡会发生变化。
 
 
让我们尝试再次选择Dev节点刷新页面。在加载帐户旁边，我之前没有使用过任何帐户，而是创建了另一个新帐户。有趣的是，您可以将此帐户作为单独的密钥库文件或密钥下载并重复使用。如果您在另一台计算机上进行测试，则可能需要继续使用您使用的帐户。您可以在此时使用此选项。例如，如果您单击某个帐户，则会有一个备用当前帐户。选择它后，将打开一个窗口，您可以选择接收密钥库或密钥。只需备份您的密钥即可。单击“复制到剪贴板”时，您现在已备份此帐户的密钥。
 
 
然后再次刷新页面。创建帐户后，再次单击并选择导入帐户选项。转到私钥选项卡并粘贴备份的密钥。显示标签将被称为测试帐户。进口。如果您再次选择该帐户，您将拥有我们在下面导入的测试帐户。因此，当您以这种方式或在另一台计算机上返回此页面时，您可以始终如一地进行测试。
 
 
我将尝试首先部署它，而不是解释Tx值。部署
。单击编译按钮后，您可以选择部署我们的AdditionGame。部署单击。然后，部署在不到3秒的时间内完成。中间面板中有一个TX哈希，对吧？这是部署生成的事务哈希信息。最重要的是，它显示了部署合同地址的地址。
 
 
如果查看旁边的面板，您将看到当前部署了合同的地址，下面您可以选择加载所有者状态变量的值。这是一个getter函数。由于我们已声明状态变量所有者public的可见性，因此我们可以自动生成getter函数以检索所有者变量的值。按“呼叫”按钮时，将显示以下地址。这是什么地址？
 
是这是部署此合同的人员的帐户地址。我已使用来自帐户的帐户部署合同，因此此帐户将保存为状态变量所有者的值。是的，我通过Klaytn IDE编写了可靠性代码并测试了合同所有者。接下来，我们将编写并测试下一课程中剩余的两个函数。




 
## 4.4 Klaytn IDE & Smart Contract 2
 

让我们继续创建一个函数，查看合同地址中剩余的KLAY余额数量。请选中旁边的自动复选框。在构造函数中，我们将创建一个getBalance函数。

使用function关键字，名称为getBalance（），可见性为public，类型为只读视图。最后，将uint类型定义为返回的函数。

地址（this）是指当前合同本身。这是版本游戏合约。并且可以作为会员使用平衡。这样就完成了在此合同地址加载KLAY余额的功能。让我们重新部署它进行测试。单击Deploy按钮，然后创建getBalance（）函数并激活Call按钮。我们点击这一次。然后当前余额为零。我还没发送任何东西。
 
 
接下来，让我们创建一个函数，将KLAY从所有者帐户发送到合同地址。

我公开了可见性，并且应付了类型。每当您将KLAY发送到帐户中的可靠性功能时，您必须始终将类型设为应付款。这样我就能从这个功能中获得收益。接下来，我们将检查有效性。

如果不使用require关键字，则该函数将被终止。 msg.sender是指现在调用此函数的帐户，并将该帐户与状态变量所有者帐户进行比较，这样，如果当前加载此函数的帐户不是所有者帐户，则不会执行该函数。所以我检查了有效性检查，看看我是否可以将KLAY从所有者帐户转移到合同中。现在，让我们试试吧。
 
 
请按“部署”按钮。存款功能现已激活。如果您使用存款功能发送KLAY，则必须使用Tx.value。如果函数具有应付款类型，则必须使用tx.value。在其旁边的test_KLAY中，输入1作为值。然后单击存款发送按钮。您的交易成功并返回了一个交易收据。如果您从来自帐户查看帐户，余额将从100 KLAY减少到99 KLAY。如果这是原始的，我们将不得不扣除余额，包括用于处理交易的天然气成本，但我们选择了dev节点，其中不包括开发节点或天然气账单。
 

现在让我们调用getbalance函数来查看合约余额是多少。它包含一个值。请注意，我们只发送了1个KLAY，而且数量太大，您可能会感到困惑。现在这是1 KLAY的值转换为peb，KLAY的最小单位。在Klayton虚拟机中，您需要将KLAY转换为最小的peb单位并对其进行处理，因此您可以看到此数字。从tx值键入值并将其发送到存储函数时，谢天谢地，IDE会自动将其转换为最小的单位peb。
这是一个非常有用的测试功能。相反，您也可以使用tx值中的不同单位进行测试，这次使用最低单位peb。让我们将2个KLAY转换为peb并将其发送给合同。返回单位转换网站，输入2个KLAY，将转换后的值复制到peb，然后将其粘贴到tx值。
 
 
然后你调用存款功能。交易成功。我们来调用getbalance函数。然后价值增加。我了解到你可以用单位转换进行测试。
 
 

气体限制是气体的限制，默认为自动。换句话说，它计算进入功能的气体限制并自动定义它。这是因为计算取决于函数的复杂性。因此功能处理的气体限制不固定。当我们从前一个路线发送钱包钱时，气体限制固定在25000.这只是一个汇款的交易，所以没有复杂性，气体限制是固定的。实际上，您可以手动输入此气体限制并尝试更精确的测试。到目前为止，我已经了解了天然气限制，并且我已经涵盖了使用交易价值从合同转移资金的方式。
 

 
## 4.5 Klaytn IDE & Smart Contract 3
 

使用这最后一个函数，让我们写一个逻辑，当用户解决了加法游戏的问题时，将合同中的钱转移到用户帐户。作为参考，回答正确答案的用户直接调用此功能来接收钱。
 
获取KLAY值作为参数传递给用户。请注意，此值从前端转换为peb并传递。还有一个返回布尔值的函数。接下来，您需要验证合同中的余额是否等于您要发送给用户的值。
 

调用上面的getbalance（）函数调用当前合约中的剩余余额，如果它等于或大于作为参数接收的值，则传递它。
 

msg.sender，具有正确答案的用户已调用此功能（转移（_value））以获得奖金并使用转移功能将KLAY发送给用户。最后，我会回归成功。
 

现在我们已经编写了我们将使用的智能合约代码。这很简单。现在让我们做最后的测试。要部署，请将Tx值设置为0并将气体限制设置回自动。您的部署成功。为了使用转移功能，我们将再次发送KLAY，因为新部署后合同余额为0。 Tx值为3，我将Test_peb更改为Test_klay。按存款功能中的发送按钮。如果交易成功，请点击“获取余额”，您的资金进入。请记住，我的帐户余额为94 KLAY。
 

现在让我们使用传递函数。将Tx值设置回0并单击传递函数的发送按钮。现在，这是一个包含参数的函数，您必须在窗口出现时发送参数值。您还必须在发送时将KLAY转换为peb。请记住，发送给合同的KLAY值将转换为peb并通过。返回转换网站并转换1个KLAY。复制并粘贴Peb值。按下呼叫按钮，将执行交易，并且将成功返回收据。 “来自账户”的余额增加了一倍。就在之前是94 KLAY。最后，当调用getbalance函数时，总共剩下2个KLAY，其中1个KLAY减少。
 

作为参考，该dev节点是实际运行的节点，因此，我们所做的事务的跟踪将被记录在网络中。你是如何测试的？所有你必须知道的是合同地址。部署按钮下的信息是我们部署到dev节点的合同地址。复制此并刷新页面。
 

再次单击编译按钮，然后单击添加游戏箭头。在它下面，再次粘贴合同地址。然后再次激活这些功能。我们来调用Getbalance函数。您的余额将保持与以前相同的金额。这很简单。如果您只知道对方地址，则可以看到我测试过的记录。到目前为止，我们已经使用Klaytn IDE研究了添加游戏的添加和测试。
