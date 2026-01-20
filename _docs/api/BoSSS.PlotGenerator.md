---
title: "BoSSS.PlotGenerator"
parent: "API Reference"
nav_order: 8
permalink: /docs/api/BoSSS.PlotGenerator/
---
# Namespace: BoSSS.PlotGenerator

## Class: BoSSS.PlotGenerator.FieldStateConfiguration <a id="bosss.plotgenerator.fieldstateconfiguration"></a>

**Summary:** Class representing a configuration of field states. Can be used as an
exchange format for settings for a list of fields

## Class: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats <a id="bosss.plotgenerator.fieldstateconfiguration.exportformats"></a>

**Summary:** Supported export formats


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats.TecPlot <a id="bosss.plotgenerator.fieldstateconfiguration.exportformats.tecplot"></a>
**Summary:** Create binary Tecplot file


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats.Cgns <a id="bosss.plotgenerator.fieldstateconfiguration.exportformats.cgns"></a>
**Summary:** The CGNS format


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats.Hdf5 <a id="bosss.plotgenerator.fieldstateconfiguration.exportformats.hdf5"></a>
**Summary:** CGNS via Hdf5


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats.CSV <a id="bosss.plotgenerator.fieldstateconfiguration.exportformats.csv"></a>
**Summary:** generic ASCII files: see
[BoSSS.Solution.ASCIIExport.CSVExportDriver](BoSSS.Solution.ASCIIExport.md#bosss.solution.asciiexport.csvexportdriver)


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats.Curve <a id="bosss.plotgenerator.fieldstateconfiguration.exportformats.curve"></a>
**Summary:** VisIts curve file: see
[BoSSS.Solution.ASCIIExport.CurveExportDriver](BoSSS.Solution.ASCIIExport.md#bosss.solution.asciiexport.curveexportdriver)


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats.BinaryStream <a id="bosss.plotgenerator.fieldstateconfiguration.exportformats.binarystream"></a>
**Summary:** Binary stream as it is for example used by Matlab; see
[BoSSS.Solution.ASCIIExport.BinaryStreamExportDriver](BoSSS.Solution.ASCIIExport.md#bosss.solution.asciiexport.binarystreamexportdriver)

## Class: BoSSS.PlotGenerator.FieldStateConfiguration.ReconstructionTypes <a id="bosss.plotgenerator.fieldstateconfiguration.reconstructiontypes"></a>

**Summary:** Supported reconstruction types for the originally discontinuous
data


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ReconstructionTypes.None <a id="bosss.plotgenerator.fieldstateconfiguration.reconstructiontypes.none"></a>
**Summary:** No reconstruction, export as is


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ReconstructionTypes.Average <a id="bosss.plotgenerator.fieldstateconfiguration.reconstructiontypes.average"></a>
**Summary:** Build the node-wise average of all values

## Class: BoSSS.PlotGenerator.FieldStateConfiguration.GhostLevels <a id="bosss.plotgenerator.fieldstateconfiguration.ghostlevels"></a>

**Summary:** Supported ghost levels


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.GhostLevels.Zero <a id="bosss.plotgenerator.fieldstateconfiguration.ghostlevels.zero"></a>
**Summary:** No overlap, export as is


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.GhostLevels.One <a id="bosss.plotgenerator.fieldstateconfiguration.ghostlevels.one"></a>
**Summary:** Mesh overlap of on unit (element)


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.BasePaths <a id="bosss.plotgenerator.fieldstateconfiguration.basepaths"></a>
**Summary:** The paths to the databases


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.SessionGuid <a id="bosss.plotgenerator.fieldstateconfiguration.sessionguid"></a>
**Summary:** The selected session


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.FieldNames <a id="bosss.plotgenerator.fieldstateconfiguration.fieldnames"></a>
**Summary:** The fields selected for export


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.TimeSteps <a id="bosss.plotgenerator.fieldstateconfiguration.timesteps"></a>
**Summary:** The time-step numbers of the time-steps


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.SuperSampling <a id="bosss.plotgenerator.fieldstateconfiguration.supersampling"></a>
**Summary:** The selected value for super sampling


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.PlotShadowFields <a id="bosss.plotgenerator.fieldstateconfiguration.plotshadowfields"></a>
**Summary:** Plot [BoSSS.Foundation.XDG.XDGField](BoSSS.Foundation.XDG.md#bosss.foundation.xdg.xdgfield) specieswise


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ReconstructionType <a id="bosss.plotgenerator.fieldstateconfiguration.reconstructiontype"></a>
**Summary:** The selected reconstruction type


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.GhostLevel <a id="bosss.plotgenerator.fieldstateconfiguration.ghostlevel"></a>
**Summary:** The selected ghost level


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.NumberOfProcesses <a id="bosss.plotgenerator.fieldstateconfiguration.numberofprocesses"></a>
**Summary:** The number of processes that should be used for the export


### Field: BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormat <a id="bosss.plotgenerator.fieldstateconfiguration.exportformat"></a>
**Summary:** The selected export format


## Method: BoSSS.PlotGenerator.FieldStateConfiguration.Serialize(System.String,BoSSS.PlotGenerator.FieldStateConfiguration) <a id="bosss.plotgenerator.fieldstateconfiguration.serialize(system.string,bosss.plotgenerator.fieldstateconfiguration)"></a>
**Summary:** Uses a **System.Runtime.Serialization.DataContractSerializer** to serialize the given
'config'
**Parameter:** `fileName` - The name of the file to be created
**Parameter:** `config` - The configuration to be serialized


## Method: BoSSS.PlotGenerator.FieldStateConfiguration.Deserialize(System.String) <a id="bosss.plotgenerator.fieldstateconfiguration.deserialize(system.string)"></a>
**Summary:** Uses a **System.Runtime.Serialization.DataContractSerializer** to de-serialize the
configuration stored in 'fileName'
**Parameter:** `fileName` - The name of the file containing the serialized configuration
**Returns:**
The deserialized configuration or null if the deserialization
failed


## Method: BoSSS.PlotGenerator.FieldStateConfiguration.LoadConfig(System.String) <a id="bosss.plotgenerator.fieldstateconfiguration.loadconfig(system.string)"></a>
**Summary:** Uses a **System.Xml.Serialization.XmlSerializer** to de-serialize the content of a
file with the name 'fileName'.
**Parameter:** `fileName` - 


## Method: BoSSS.PlotGenerator.FieldStateConfiguration.Equals(BoSSS.PlotGenerator.FieldStateConfiguration) <a id="bosss.plotgenerator.fieldstateconfiguration.equals(bosss.plotgenerator.fieldstateconfiguration)"></a>
**Summary:** Basically compares this object to 'other' by
comparing all public attributes for equality
**Parameter:** `other` - An object to be compared to
**Returns:**
True, if all public attributes are equal; false otherwise


## Method: BoSSS.PlotGenerator.FieldStateConfiguration.Clear(BoSSS.PlotGenerator.FieldStateConfiguration.ReconstructionTypes,BoSSS.PlotGenerator.FieldStateConfiguration.GhostLevels,BoSSS.PlotGenerator.FieldStateConfiguration.ExportFormats) <a id="bosss.plotgenerator.fieldstateconfiguration.clear(bosss.plotgenerator.fieldstateconfiguration.reconstructiontypes,bosss.plotgenerator.fieldstateconfiguration.ghostlevels,bosss.plotgenerator.fieldstateconfiguration.exportformats)"></a>
**Summary:** Clears all data in public attributes
**Parameter:** `defaultReconstructionType` - The initially selected reconstruction type
**Parameter:** `defaultExportFormat` - The initially selected export format
**Parameter:** `defaultGhostLevel` - 

## Class: BoSSS.PlotGenerator.PlotApplication <a id="bosss.plotgenerator.plotapplication"></a>

**Summary:** Actual implementation of the plot generation using the BoSSS API for
convenience reasons

Container for the main entry point


### Property: BoSSS.PlotGenerator.PlotApplication.ForceXDGLinking <a id="bosss.plotgenerator.plotapplication.forcexdglinking"></a>
**Summary:** No Real functionality; this just forces the compiler to link the XDG dll.


### Field: BoSSS.PlotGenerator.PlotApplication.m_format <a id="bosss.plotgenerator.plotapplication.m_format"></a>
**Summary:** The format of the plot file


### Field: BoSSS.PlotGenerator.PlotApplication.m_path <a id="bosss.plotgenerator.plotapplication.m_path"></a>
**Summary:** The destination of the plot file


### Field: BoSSS.PlotGenerator.PlotApplication.m_config <a id="bosss.plotgenerator.plotapplication.m_config"></a>
**Summary:** De-serialized configuration options


### Field: BoSSS.PlotGenerator.PlotApplication.m_info <a id="bosss.plotgenerator.plotapplication.m_info"></a>
**Summary:** Session information


### Field: BoSSS.PlotGenerator.PlotApplication.m_PlotDriver <a id="bosss.plotgenerator.plotapplication.m_plotdriver"></a>
**Summary:** Handle for the plot driver


### Field: BoSSS.PlotGenerator.PlotApplication.m_showJumps <a id="bosss.plotgenerator.plotapplication.m_showjumps"></a>
**Summary:** Indicates whether jumps should be shown or whether values should be
averaged at congruent nodes


### Field: BoSSS.PlotGenerator.PlotApplication.m_GhostZone <a id="bosss.plotgenerator.plotapplication.m_ghostzone"></a>
**Summary:** Indicates whether ghost overlap should be shown


## Method: BoSSS.PlotGenerator.PlotApplication.#ctor(BoSSS.PlotGenerator.FieldStateConfiguration,System.String) <a id="bosss.plotgenerator.plotapplication.#ctor(bosss.plotgenerator.fieldstateconfiguration,system.string)"></a>
**Summary:** Saves the 'config' and the 'path'
and determines the reconstruction type ([BoSSS.PlotGenerator.PlotApplication.m_showJumps](#bosss.plotgenerator.plotapplication.m_showjumps)) and
ghost level ([BoSSS.PlotGenerator.PlotApplication.m_GhostZone](#bosss.plotgenerator.plotapplication.m_ghostzone))
from the 'config'.
**Parameter:** `config` - Configuration options
**Parameter:** `path` - The output path


### Property: BoSSS.PlotGenerator.PlotApplication.DBDriver <a id="bosss.plotgenerator.plotapplication.dbdriver"></a>
**Summary:** The driver of the database containing the data to be plotted.


### Property: BoSSS.PlotGenerator.PlotApplication.GridDat <a id="bosss.plotgenerator.plotapplication.griddat"></a>
**Summary:** the grid


## Method: BoSSS.PlotGenerator.PlotApplication.Run <a id="bosss.plotgenerator.plotapplication.run"></a>
**Summary:** Override the original run method defined by the super-class because
we don't want to run an actual calculation. Plots the data for
every selected time-step.


## Method: BoSSS.PlotGenerator.PlotApplication.GetDatabase <a id="bosss.plotgenerator.plotapplication.getdatabase"></a>
**Summary:** Returns a "lightweight" object that stores information about the current database.
**Returns:**



## Method: BoSSS.PlotGenerator.PlotApplication.CreatePlotter <a id="bosss.plotgenerator.plotapplication.createplotter"></a>
**Summary:** Initializes the plot driver


## Method: BoSSS.PlotGenerator.PlotApplication.PlotCurrentState(System.Collections.Generic.IEnumerable{BoSSS.Foundation.DGField},System.Double,BoSSS.Foundation.IO.TimestepNumber) <a id="bosss.plotgenerator.plotapplication.plotcurrentstate(system.collections.generic.ienumerable{bosss.foundation.dgfield},system.double,bosss.foundation.io.timestepnumber)"></a>
**Summary:** Actual plotting routine which uses
[BoSSS.Solution.PlotDriver.PlotFields(System.String,System.Double,System.Collections.Generic.IEnumerable{BoSSS.Foundation.DGField})](BoSSS.Solution.md#bosss.solution.plotdriver.plotfields(system.string,system.double,system.collections.generic.ienumerable{bosss.foundation.dgfield}))
to plot a single time-step
**Parameter:** `fields` - 
**Parameter:** `physTime` - 
**Parameter:** `timestepNo` - 


## Method: BoSSS.PlotGenerator.PlotApplication.Main(System.String[]) <a id="bosss.plotgenerator.plotapplication.main(system.string[])"></a>
**Summary:** Main entry point. Uses [BoSSS.PlotGenerator.PlotApplication](#bosss.plotgenerator.plotapplication) to plot all fields
referenced in the config file supplied as a command line argument
**Parameter:** `args` - Command line arguments. Currently, only the first entry is used
which has to contain the path to the configuration file containing
the plot information



