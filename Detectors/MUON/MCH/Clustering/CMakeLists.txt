# Copyright CERN and copyright holders of ALICE O2. This software is distributed
# under the terms of the GNU General Public License v3 (GPL Version 3), copied
# verbatim in the file "COPYING".
#
# See http://alice-o2.web.cern.ch/license for full licensing information.
#
# In applying this license CERN does not waive the privileges and immunities
# granted to it by virtue of its status as an Intergovernmental Organization or
# submit itself to any jurisdiction.
find_package(GSL REQUIRED)

o2_add_library(MCHClustering
               SOURCES src/ClusterDump.cxx
                       src/dataStructure.cxx
                       src/ClusterOriginal.cxx
                       src/ClusterFinderOriginal.cxx
                       src/MathiesonOriginal.cxx
               PUBLIC_LINK_LIBRARIES O2::MCHMappingInterface O2::MCHBase O2::MCHPreClustering O2::Framework)
               
o2_add_library(MCHClusteringGEM
               SOURCES src/MathiesonOriginal.cxx               	
                       src/ClusterOriginal.cxx
                       src/ClusterFinderOriginal.cxx
                       src/ClusterDump.cxx
                       src/ClusterFinderGEM.cxx
                       src/dataStructure.cxx
                       src/mathUtil.cxx
                       src/padProcessing.cxx
                       src/mathiesonFit.cxx
                       src/mathieson.cxx
                       src/gaussianEM.cxx
                       src/clusterProcessing.cxx
               PUBLIC_LINK_LIBRARIES GSL::gsl O2::MCHMappingInterface O2::MCHBase O2::MCHPreClustering  O2::Framework)
