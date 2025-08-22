# fw-517-data-analysis-2025-08-22

<img width="523" height="290" alt="image" src="https://github.com/user-attachments/assets/93ce40c0-098f-48fd-87d8-ac019a5ef281" />

In[1]:= a = 
  Import["~/LR5-SSR_2025-08-17_H16_M11_S55e/LR5-SSR_2025-08-17_H16_\
M11_S55.csv", "CSV"];

In[2]:= a[[1]]

Out[2]= {"2025 Aug 17 16:11:55.271", 0.17, -8.6875, 0.375, 0.625, \
0.25, 0.5, 0.5625, 0.5, 0.5, 0.4375, 0.4375, 0, 0}

In[3]:= Length[a[[1]]]

Out[3]= 14

In[4]:= a[[1, {13, 14}]]

Out[4]= {0, 0}

In[5]:= a[[Length[a]]]

Out[5]= {"2025 Aug 22 14:24:23.520", 425548., -9.6875, 0., 0.1875, \
0., 0.1875, 0., 0., 0., 0.0625, 0.0625, 0, 1}

In[6]:= Length[a]

Out[6]= 2872088

In[7]:= 537549*.75

Out[7]= 403162.

In[8]:= b = Transpose[a];

In[9]:= b[[1]]

Out[9]= If[False, 
Missing["NotStored"], 
If[21589114782417399083 === $SessionID, 
Out[9], Message[
MessageName[Syntax, "noinfoker"]]; Missing["NotAvailable"]; Null]]

In[10]:= Length[a[[1]]]

Out[10]= 14

In[11]:= b[[2]]

Out[11]= If[False, 
Missing["NotStored"], 
If[21589114782417399083 === $SessionID, 
Out[11], Message[
MessageName[Syntax, "noinfoker"]]; Missing["NotAvailable"]; Null]]

In[12]:= c = Table[b[[k]], {k, 2, Length[b] - 2}];

In[14]:= c[[1]]

Out[14]= If[False, 
Missing["NotStored"], 
If[21589114782417399083 === $SessionID, 
Out[14], Message[
MessageName[Syntax, "noinfoker"]]; Missing["NotAvailable"]; Null]]

In[21]:= d = Table[ExportString[c[[i]], "Real32"], {i, Length[c]}];

In[22]:= e = Table[ImportString[d[[i]], "Real32"], {i, Length[d]}]

Out[22]= If[False, 
Missing["NotStored"], 
If[21589114782417399083 === $SessionID, 
Out[22], Message[
MessageName[Syntax, "noinfoker"]]; Missing["NotAvailable"]; Null]]

In[23]:= Dimensions[e]

Out[23]= {11, 2872088}

In[25]:= time = e[[1]];

In[29]:= fr = e[[2]];

In[30]:= f = Table[e[[k]], {k, 3, 11}];

In[31]:= g = Transpose[f];

In[32]:= g[[1]]

Out[32]= {0.375, 0.625, 0.25, 0.5, 0.5625, 0.5, 0.5, 0.4375, 0.4375}

In[48]:= temp = Table[Sum[g[[i, k]], {k, 9}]/9., {i, Length[g]}];

In[34]:= temp[[1]]

Out[34]= 4.1875

In[49]:= ft = Table[{time[[i]], fr[[i]]}, {i, Length[time]}];

In[50]:= tt = Table[{time[[i]], temp[[i]]}, {i, Length[time]}];

In[51]:= g1 = ListPlot[ft, PlotRange -> {-20, 10},
  Axes -> False, Frame -> True, PlotLegends -> {"Freezer"}, 
  FrameLabel -> {"time", "temp"},
  PlotStyle -> {Blue}]

In[52]:= g2 = ListPlot[tt, PlotRange -> {-20, 10},
  Axes -> False, Frame -> True, PlotLegends -> {"gadget"}, 
  FrameLabel -> {"time", "temp"},
  PlotStyle -> {Red}]

In[53]:= Show[g1, g2]
<img width="743" height="1853" alt="image" src="https://github.com/user-attachments/assets/2cb39217-d135-4082-81d3-5aaa3fddfcec" />
